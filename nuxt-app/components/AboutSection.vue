<template>
  <section class="py-20 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section header -->
      <div class="text-center mb-12">
        <h2 class="text-4xl md:text-5xl mb-4">O firmie</h2>
        <p class="text-gray-600 text-lg max-w-3xl mx-auto">
          RentCar to wypożyczalnia samochodów działająca w największych miastach Polski. Oferujemy auta 
          ekonomiczne, premium, luksusowe i elektryczne.
        </p>
        <p class="text-gray-600 text-lg max-w-3xl mx-auto mt-4">
          Od 2010 roku zapewniamy najwyższą jakość usług i kompleksową obsługę klienta. Nasza flota to ponad 500 
          nowoczesnych pojazdów, a zadowolenie klientów jest naszym priorytetem.
        </p>
      </div>

      <!-- Stats -->
      <div class="grid grid-cols-2 md:grid-cols-4 gap-8 mb-16">
        <div v-for="(stat, index) in stats" :key="index" class="text-center">
          <div class="w-16 h-16 bg-emerald-500 rounded-full flex items-center justify-center mx-auto mb-4">
            <component :is="stat.icon" class="w-8 h-8 text-white" />
          </div>
          <div class="text-3xl md:text-4xl text-emerald-500 mb-2">{{ stat.value }}</div>
          <div class="text-gray-600">{{ stat.label }}</div>
        </div>
      </div>

      <!-- Images -->
      <div class="grid md:grid-cols-3 gap-6">
        <div class="relative h-64 rounded-2xl overflow-hidden group">
          <img
            src="https://images.unsplash.com/photo-1583121274602-3e2820c69888?w=800&q=80"
            alt="Luxury red car"
            class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-300"
          />
        </div>
        <div class="relative h-64 rounded-2xl overflow-hidden group">
          <img
            src="https://images.unsplash.com/photo-1593941707882-a5bba14938c7?w=800&q=80"
            alt="Electric car charging"
            class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-300"
          />
        </div>
        <div class="relative h-64 rounded-2xl overflow-hidden group">
          <img
            src="https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?w=800&q=80"
            alt="Luxury car interior"
            class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-300"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { MapPin, Car, Users, Clock } from 'lucide-vue-next'

const stats = [
  {
    icon: MapPin,
    value: '15+',
    label: 'Lat doświadczenia',
  },
  {
    icon: Car,
    value: '500+',
    label: 'Pojazdów we flocie',
  },
  {
    icon: Users,
    value: '50k+',
    label: 'Zadowolonych klientów',
  },
  {
    icon: Clock,
    value: '24/7',
    label: 'Wsparcie klienta',
  },
]
</script>

