<template>
  <div class="bg-white">
    <!-- Hero section -->
    <section class="relative h-[400px] flex items-center justify-center overflow-hidden">
      <div class="absolute inset-0">
        <img
          src="https://images.unsplash.com/photo-1497366216548-37526070297c?w=1920&q=80"
          alt="Office"
          class="w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-gray-900/60"></div>
      </div>
      <div class="relative z-10 text-center text-white">
        <h1 class="text-5xl md:text-6xl mb-4">O nas</h1>
        <p class="text-xl max-w-2xl mx-auto px-4">
          Profesjonalna wypożyczalnia samochodów z pasją do doskonałości
        </p>
      </div>
    </section>

    <!-- Story section -->
    <section class="py-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <div>
          <h2 class="text-4xl mb-6">Nasza historia</h2>
          <p class="text-gray-600 mb-4">
            RentCar powstał w 2010 roku z prostego założenia – każdy powinien mieć dostęp do 
            wygodnego i bezpiecznego transportu, niezależnie od okazji. Zaczęliśmy od małej floty 
            20 samochodów w Warszawie, a dziś jesteśmy jedną z największych wypożyczalni w Polsce.
          </p>
          <p class="text-gray-600 mb-4">
            Przez lata zbudowaliśmy zespół profesjonalistów, którzy codziennie dbają o to, aby 
            każdy klient czuł się wyjątkowo. Nasze pojazdy to nie tylko środek transportu – to 
            gwarancja komfortu, bezpieczeństwa i niezapomnianych wrażeń z podróży.
          </p>
          <p class="text-gray-600">
            Dziś posiadamy ponad 500 pojazdów w całej Polsce, od ekonomicznych modeli miejskich 
            po luksusowe limuzyny i ekologiczne samochody elektryczne. Naszą misją jest zapewnienie 
            najwyższej jakości usług i pełnej elastyczności dla naszych klientów.
          </p>
        </div>
        <div class="grid grid-cols-2 gap-4">
          <img
            src="https://images.unsplash.com/photo-1560179707-f14e90ef3623?w=600&q=80"
            alt="Team"
            class="rounded-2xl h-64 w-full object-cover"
          />
          <img
            src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?w=600&q=80"
            alt="Office"
            class="rounded-2xl h-64 w-full object-cover mt-8"
          />
        </div>
      </div>
    </section>

    <!-- Values section -->
    <section class="py-20 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12">
          <h2 class="text-4xl mb-4">Nasze wartości</h2>
          <p class="text-gray-600 text-lg">
            Fundamenty, na których zbudowaliśmy naszą firmę
          </p>
        </div>
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div
            v-for="(value, index) in values"
            :key="index"
            class="bg-white rounded-2xl p-6 text-center hover:shadow-lg transition-shadow"
          >
            <div class="w-16 h-16 bg-emerald-100 rounded-full flex items-center justify-center mx-auto mb-4">
              <component :is="value.icon" class="w-8 h-8 text-emerald-600" />
            </div>
            <h3 class="text-xl mb-3">{{ value.title }}</h3>
            <p class="text-gray-600">{{ value.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Timeline section -->
    <section class="py-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-12">
        <h2 class="text-4xl mb-4">Nasza droga</h2>
        <p class="text-gray-600 text-lg">
          Kluczowe momenty w historii RentCar
        </p>
      </div>
      <div class="relative">
        <!-- Timeline line -->
        <div class="absolute left-1/2 transform -translate-x-1/2 h-full w-1 bg-emerald-200 hidden md:block"></div>
        
        <!-- Timeline items -->
        <div class="space-y-12">
          <div
            v-for="(milestone, index) in milestones"
            :key="index"
            :class="['flex items-center', index % 2 === 0 ? 'md:flex-row' : 'md:flex-row-reverse']"
          >
            <div :class="['w-full md:w-1/2', index % 2 === 0 ? 'md:pr-12 md:text-right' : 'md:pl-12']">
              <div class="bg-white rounded-2xl p-6 shadow-sm hover:shadow-md transition-shadow">
                <div class="text-2xl text-emerald-600 mb-2">{{ milestone.year }}</div>
                <h3 class="text-xl mb-2">{{ milestone.title }}</h3>
                <p class="text-gray-600">{{ milestone.description }}</p>
              </div>
            </div>
            <div class="hidden md:flex w-8 h-8 bg-emerald-500 rounded-full border-4 border-white shadow-md z-10 absolute left-1/2 transform -translate-x-1/2"></div>
            <div class="hidden md:block w-1/2"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Stats section -->
    <section class="py-20 bg-emerald-500">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid md:grid-cols-4 gap-8 text-center text-white">
          <div>
            <div class="text-5xl mb-2">15+</div>
            <div class="text-white/90">Lat na rynku</div>
          </div>
          <div>
            <div class="text-5xl mb-2">500+</div>
            <div class="text-white/90">Pojazdów</div>
          </div>
          <div>
            <div class="text-5xl mb-2">50k+</div>
            <div class="text-white/90">Zadowolonych klientów</div>
          </div>
          <div>
            <div class="text-5xl mb-2">12</div>
            <div class="text-white/90">Oddziałów w Polsce</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Locations -->
    <section class="py-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-12">
        <h2 class="text-4xl mb-4">Nasze lokalizacje</h2>
        <p class="text-gray-600 text-lg">
          Obecni w największych miastach Polski
        </p>
      </div>
      <div class="grid md:grid-cols-3 gap-6">
        <div
          v-for="(city, index) in cities"
          :key="index"
          class="flex items-center gap-3 bg-gray-50 rounded-xl p-6 hover:bg-gray-100 transition-colors"
        >
          <MapPin class="w-6 h-6 text-emerald-500" />
          <span class="text-lg">{{ city }}</span>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { Award, Shield, Users, TrendingUp, MapPin } from 'lucide-vue-next'

const values = [
  {
    icon: Shield,
    title: 'Bezpieczeństwo',
    description: 'Wszystkie nasze pojazdy są regularnie serwisowane i ubezpieczone. Twoje bezpieczeństwo jest dla nas priorytetem.',
  },
  {
    icon: Award,
    title: 'Jakość usług',
    description: 'Oferujemy najwyższe standardy obsługi klienta. Każdy samochód jest dokładnie sprawdzany przed wydaniem.',
  },
  {
    icon: Users,
    title: 'Doświadczenie',
    description: 'Ponad 15 lat doświadczenia w branży wynajmu samochodów. Zaufało nam już ponad 50 000 klientów.',
  },
  {
    icon: TrendingUp,
    title: 'Innowacyjność',
    description: 'Stale rozwijamy naszą ofertę, wprowadzając pojazdy elektryczne i nowoczesne systemy rezerwacji online.',
  },
]

const milestones = [
  { year: '2010', title: 'Założenie firmy', description: 'Rozpoczęcie działalności z flotą 20 pojazdów' },
  { year: '2013', title: 'Ekspansja', description: 'Otwarcie oddziałów w 5 największych miastach Polski' },
  { year: '2017', title: 'Nowoczesność', description: 'Wprowadzenie systemu rezerwacji online i aplikacji mobilnej' },
  { year: '2020', title: 'Ekologia', description: 'Dodanie samochodów elektrycznych do floty' },
  { year: '2024', title: 'Lider rynku', description: 'Ponad 500 pojazdów i 50 000+ zadowolonych klientów' },
]

const cities = ['Warszawa', 'Kraków', 'Wrocław', 'Poznań', 'Gdańsk', 'Katowice']
</script>

