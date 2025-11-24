<template>
  <div class="bg-white">
    <!-- Hero section -->
    <section class="relative h-[400px] flex items-center justify-center overflow-hidden">
      <div class="absolute inset-0">
        <img
          src="https://images.unsplash.com/photo-1492144534655-ae79c964c9d7?w=1920&q=80"
          alt="Cars"
          class="w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-gray-900/60"></div>
      </div>
      <div class="relative z-10 text-center text-white">
        <h1 class="text-5xl md:text-6xl mb-4">Nasza Oferta</h1>
        <p class="text-xl max-w-2xl mx-auto px-4">
          Szeroki wybór pojazdów dopasowanych do Twoich potrzeb
        </p>
      </div>
    </section>

    <!-- Categories filter -->
    <section class="py-8 bg-gray-50 sticky top-0 z-40 border-b border-gray-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-wrap gap-3 justify-center">
          <button
            v-for="category in categories"
            :key="category.id"
            @click="selectedCategory = category.id"
            :class="[
              'flex items-center gap-2 px-6 py-3 rounded-lg transition-all',
              selectedCategory === category.id
                ? 'bg-emerald-500 text-white shadow-md'
                : 'bg-white text-gray-700 hover:bg-gray-100'
            ]"
          >
            <component :is="category.icon" class="w-5 h-5" />
            {{ category.name }}
          </button>
        </div>
      </div>
    </section>

    <!-- Cars grid -->
    <section class="py-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div
          v-for="(car, index) in filteredCars"
          :key="index"
          class="bg-white rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-shadow border border-gray-100"
        >
          <!-- Car image -->
          <div class="relative h-48 overflow-hidden">
            <img
              :src="car.image"
              :alt="car.name"
              class="w-full h-full object-cover hover:scale-105 transition-transform duration-300"
            />
            <div class="absolute top-4 right-4 bg-emerald-500 text-white px-3 py-1 rounded-full text-sm">
              {{ car.price }} zł/dzień
            </div>
          </div>

          <!-- Car details -->
          <div class="p-6">
            <h3 class="text-2xl mb-4">{{ car.name }}</h3>

            <!-- Specs -->
            <div class="grid grid-cols-3 gap-3 mb-4 text-sm">
              <div class="flex items-center gap-2 text-gray-600">
                <Users class="w-4 h-4" />
                {{ car.passengers }}
              </div>
              <div class="flex items-center gap-2 text-gray-600">
                <Settings class="w-4 h-4" />
                {{ car.transmission }}
              </div>
              <div class="flex items-center gap-2 text-gray-600">
                <Fuel class="w-4 h-4" />
                {{ car.fuel }}
              </div>
            </div>

            <!-- Features -->
            <div class="border-t border-gray-100 pt-4 mb-4">
              <ul class="space-y-2">
                <li
                  v-for="(feature, featureIndex) in car.features"
                  :key="featureIndex"
                  class="flex items-center gap-2 text-sm text-gray-600"
                >
                  <Check class="w-4 h-4 text-emerald-500" />
                  {{ feature }}
                </li>
              </ul>
            </div>

            <!-- CTA -->
            <button class="w-full bg-emerald-500 text-white py-3 rounded-lg hover:bg-emerald-600 transition-colors">
              Zarezerwuj teraz
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Additional services -->
    <section class="py-20 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12">
          <h2 class="text-4xl mb-4">Dodatkowe usługi</h2>
          <p class="text-gray-600 text-lg">
            Uzupełnij swoją rezerwację o dodatkowe opcje
          </p>
        </div>
        <div class="grid md:grid-cols-3 gap-8">
          <div class="bg-white rounded-2xl p-8 text-center">
            <div class="w-16 h-16 bg-emerald-100 rounded-full flex items-center justify-center mx-auto mb-4">
              <Shield class="w-8 h-8 text-emerald-600" />
            </div>
            <h3 class="text-xl mb-3">Dodatkowe ubezpieczenie</h3>
            <p class="text-gray-600 mb-4">
              Rozszerz ochronę o zerowy udział własny w szkodzie
            </p>
            <div class="text-2xl text-emerald-600">Od 30 zł/dzień</div>
          </div>
          <div class="bg-white rounded-2xl p-8 text-center">
            <div class="w-16 h-16 bg-emerald-100 rounded-full flex items-center justify-center mx-auto mb-4">
              <Users class="w-8 h-8 text-emerald-600" />
            </div>
            <h3 class="text-xl mb-3">Dodatkowy kierowca</h3>
            <p class="text-gray-600 mb-4">
              Pozwól prowadzić samochód kolejnej osobie
            </p>
            <div class="text-2xl text-emerald-600">50 zł</div>
          </div>
          <div class="bg-white rounded-2xl p-8 text-center">
            <div class="w-16 h-16 bg-emerald-100 rounded-full flex items-center justify-center mx-auto mb-4">
              <Car class="w-8 h-8 text-emerald-600" />
            </div>
            <h3 class="text-xl mb-3">Dostawa samochodu</h3>
            <p class="text-gray-600 mb-4">
              Dowozimy samochód pod wskazany adres
            </p>
            <div class="text-2xl text-emerald-600">Od 100 zł</div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import { Car, Zap, Briefcase, Users, Fuel, Settings, Shield, Check } from 'lucide-vue-next'

const selectedCategory = ref('all')

const categories = [
  { id: 'all', name: 'Wszystkie', icon: Car },
  { id: 'economy', name: 'Ekonomiczne', icon: Car },
  { id: 'premium', name: 'Premium', icon: Briefcase },
  { id: 'electric', name: 'Elektryczne', icon: Zap },
  { id: 'suv', name: 'SUV', icon: Users },
]

const cars = [
  {
    category: 'economy',
    name: 'Skoda Fabia',
    image: 'https://images.unsplash.com/photo-1590362891991-f776e747a588?w=800&q=80',
    passengers: 5,
    transmission: 'Manualna',
    fuel: 'Benzyna',
    price: '150',
    features: ['Klimatyzacja', 'Radio', 'USB'],
  },
  {
    category: 'economy',
    name: 'VW Polo',
    image: 'https://images.unsplash.com/photo-1552519507-da3b142c6e3d?w=800&q=80',
    passengers: 5,
    transmission: 'Automatyczna',
    fuel: 'Benzyna',
    price: '180',
    features: ['Klimatyzacja', 'Bluetooth', 'Czujniki parkowania'],
  },
  {
    category: 'premium',
    name: 'BMW Seria 5',
    image: 'https://images.unsplash.com/photo-1555215695-3004980ad54e?w=800&q=80',
    passengers: 5,
    transmission: 'Automatyczna',
    fuel: 'Diesel',
    price: '350',
    features: ['Skórzana tapicerka', 'GPS', 'Kamera cofania', 'Asystent parkowania'],
  },
  {
    category: 'premium',
    name: 'Audi A6',
    image: 'https://images.unsplash.com/photo-1606664515524-ed2f786a0bd6?w=800&q=80',
    passengers: 5,
    transmission: 'Automatyczna',
    fuel: 'Diesel',
    price: '370',
    features: ['Virtual Cockpit', 'Bang & Olufsen', 'Matrix LED', 'Masaż foteli'],
  },
  {
    category: 'electric',
    name: 'Tesla Model 3',
    image: 'https://images.unsplash.com/photo-1560958089-b8a1929cea89?w=800&q=80',
    passengers: 5,
    transmission: 'Automatyczna',
    fuel: 'Elektryczny',
    price: '400',
    features: ['Autopilot', '500km zasięg', 'Szybkie ładowanie', 'Premium audio'],
  },
  {
    category: 'electric',
    name: 'VW ID.4',
    image: 'https://images.unsplash.com/photo-1593941707882-a5bba14938c7?w=800&q=80',
    passengers: 5,
    transmission: 'Automatyczna',
    fuel: 'Elektryczny',
    price: '320',
    features: ['450km zasięg', 'Szybkie ładowanie', 'AR HUD', 'Kamera 360°'],
  },
  {
    category: 'suv',
    name: 'Mazda CX-5',
    image: 'https://images.unsplash.com/photo-1619767886558-efdc259cde1a?w=800&q=80',
    passengers: 5,
    transmission: 'Automatyczna',
    fuel: 'Benzyna',
    price: '280',
    features: ['AWD', 'Bose audio', 'Kamera 360°', 'Tempomat adaptacyjny'],
  },
  {
    category: 'suv',
    name: 'Toyota RAV4',
    image: 'https://images.unsplash.com/photo-1581578017093-cd30lb82cd0f?w=800&q=80',
    passengers: 5,
    transmission: 'Automatyczna',
    fuel: 'Hybrid',
    price: '300',
    features: ['Hybrid', 'AWD', 'JBL audio', 'Safety Sense'],
  },
]

const filteredCars = computed(() => {
  return selectedCategory.value === 'all'
    ? cars
    : cars.filter(car => car.category === selectedCategory.value)
})
</script>

