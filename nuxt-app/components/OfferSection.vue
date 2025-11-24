<template>
  <section class="py-20 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section header -->
      <div class="text-center mb-12">
        <h2 class="text-4xl md:text-5xl mb-4">Nasza Oferta</h2>
        <p class="text-gray-600 text-lg max-w-2xl mx-auto">
          Wybierz spośród szerokiej gamy pojazdów dopasowanych do Twoich potrzeb
        </p>
      </div>

      <!-- Offer cards -->
      <div class="grid md:grid-cols-3 gap-6">
        <!-- Personal cars -->
        <div class="bg-white rounded-2xl p-8 shadow-sm hover:shadow-md transition-shadow border border-gray-100">
          <div class="w-16 h-16 bg-emerald-100 rounded-full flex items-center justify-center mb-6">
            <Car class="w-8 h-8 text-emerald-600" />
          </div>
          <h3 class="text-2xl mb-3">Samochody osobowe</h3>
          <p class="text-gray-600 mb-6">
            Szeroki wybór samochodów kompaktowych, sedan i SUV. Idealne na co dzień i dłuższe podróże.
          </p>
          <ul class="space-y-2 mb-6">
            <li class="flex items-start gap-2 text-gray-700">
              <span class="text-emerald-500 mt-1">•</span>
              <span>VW Golf, Skoda Octavia</span>
            </li>
            <li class="flex items-start gap-2 text-gray-700">
              <span class="text-emerald-500 mt-1">•</span>
              <span>Toyota Corolla, Honda Civic</span>
            </li>
            <li class="flex items-start gap-2 text-gray-700">
              <span class="text-emerald-500 mt-1">•</span>
              <span>SUV: Nissan Qashqai, Mazda CX-5</span>
            </li>
          </ul>
          <button class="text-emerald-600 hover:text-emerald-700 flex items-center gap-2 group">
            Zobacz szczegóły
            <ArrowRight class="w-4 h-4 group-hover:translate-x-1 transition-transform" />
          </button>
        </div>

        <!-- Electric cars -->
        <div class="bg-white rounded-2xl p-8 shadow-sm hover:shadow-md transition-shadow border border-gray-100">
          <div class="w-16 h-16 bg-emerald-100 rounded-full flex items-center justify-center mb-6">
            <Zap class="w-8 h-8 text-emerald-600" />
          </div>
          <h3 class="text-2xl mb-3">Samochody elektryczne</h3>
          <p class="text-gray-600 mb-6">
            Ekologiczne i nowoczesne pojazdy elektryczne. Oszczędność i troska o środowisko.
          </p>
          <ul class="space-y-2 mb-6">
            <li class="flex items-start gap-2 text-gray-700">
              <span class="text-emerald-500 mt-1">•</span>
              <span>Tesla Model 3, Model Y</span>
            </li>
            <li class="flex items-start gap-2 text-gray-700">
              <span class="text-emerald-500 mt-1">•</span>
              <span>Nissan Leaf, VW ID.3</span>
            </li>
            <li class="flex items-start gap-2 text-gray-700">
              <span class="text-emerald-500 mt-1">•</span>
              <span>Hyundai Ioniq, Kia EV6</span>
            </li>
          </ul>
          <button class="text-emerald-600 hover:text-emerald-700 flex items-center gap-2 group">
            Zobacz szczegóły
            <ArrowRight class="w-4 h-4 group-hover:translate-x-1 transition-transform" />
          </button>
        </div>

        <!-- With driver -->
        <div class="bg-white rounded-2xl p-8 shadow-sm hover:shadow-md transition-shadow border-2 border-emerald-500 relative">
          <div class="absolute top-6 right-6">
            <span class="bg-emerald-500 text-white text-xs px-3 py-1 rounded-full">
              Polecamy
            </span>
          </div>
          <div class="w-16 h-16 bg-emerald-100 rounded-full flex items-center justify-center mb-6">
            <UserCircle class="w-8 h-8 text-emerald-600" />
          </div>
          <h3 class="text-2xl mb-3">Wynajem z kierowcą</h3>
          <p class="text-gray-600 mb-6">
            Profesjonalna obsługa i komfort podróży. Doświadczeni kierowcy i luksusowe pojazdy.
          </p>
          <ul class="space-y-2 mb-6">
            <li class="flex items-start gap-2 text-gray-700">
              <span class="text-emerald-500 mt-1">•</span>
              <span>Mercedes S-Class, BMW 7</span>
            </li>
            <li class="flex items-start gap-2 text-gray-700">
              <span class="text-emerald-500 mt-1">•</span>
              <span>Audi A8, Mercedes V-Class Panorama</span>
            </li>
            <li class="flex items-start gap-2 text-gray-700">
              <span class="text-emerald-500 mt-1">•</span>
              <span>Transfer VIP, obsługa eventów</span>
            </li>
          </ul>
          <button class="w-full bg-emerald-500 text-white px-6 py-3 rounded-lg hover:bg-emerald-600 transition-colors flex items-center justify-center gap-2">
            Zapytaj o ofertę
            <ArrowRight class="w-4 h-4" />
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Car, Zap, UserCircle, ArrowRight } from 'lucide-vue-next'
</script>

