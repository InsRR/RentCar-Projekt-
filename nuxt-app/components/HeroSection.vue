<template>
  <section class="relative h-[600px] flex items-center justify-center overflow-hidden">
    <!-- Background image with overlay -->
    <div class="absolute inset-0">
      <img
        src="https://images.unsplash.com/photo-1603584173870-7f23fdae1b7a?w=1920&q=80"
        alt="Luxury car"
        class="w-full h-full object-cover"
      />
      <div class="absolute inset-0 bg-black/40"></div>
    </div>

    <!-- Content -->
    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
      <!-- Badge -->
      <div class="inline-flex items-center gap-2 bg-white/10 backdrop-blur-sm border border-white/20 rounded-full px-4 py-2 mb-6">
        <span class="text-orange-400">⚡</span>
        <span class="text-white text-sm">
          Profesjonalna wypożyczalnia od 2010 roku
        </span>
      </div>

      <!-- Main heading -->
      <h1 class="text-white mb-4">
        <div class="text-5xl md:text-6xl lg:text-7xl mb-2">
          RentCar – Twój samochód,
        </div>
        <div class="text-5xl md:text-6xl lg:text-7xl">Twój komfort</div>
      </h1>

      <!-- Description -->
      <p class="text-white/90 text-lg md:text-xl max-w-3xl mx-auto mb-8">
        Ponad 500 pojazdów w całej Polsce. Od aut miejskich po luksusowe limuzyny. 
        Rezerwuj online w 2 minuty.
      </p>

      <!-- CTA Buttons -->
      <div class="flex flex-col sm:flex-row items-center justify-center gap-4 mb-12">
        <button class="bg-emerald-500 text-white px-8 py-4 rounded-lg hover:bg-emerald-600 transition-colors flex items-center gap-2 w-full sm:w-auto justify-center">
          <Calendar class="w-5 h-5" />
          Zarezerwuj teraz
        </button>
        <button class="bg-white/10 backdrop-blur-sm text-white px-8 py-4 rounded-lg hover:bg-white/20 transition-colors border border-white/20 w-full sm:w-auto">
          Zobacz cennik
        </button>
      </div>

      <!-- Features -->
      <div class="flex flex-wrap items-center justify-center gap-6 md:gap-12">
        <div class="flex items-center gap-3 text-white">
          <div class="w-8 h-8 bg-emerald-500/20 rounded-full flex items-center justify-center">
            <Shield class="w-4 h-4 text-emerald-400" />
          </div>
          <span class="text-sm md:text-base">Pełne ubezpieczenie</span>
        </div>
        <div class="flex items-center gap-3 text-white">
          <div class="w-8 h-8 bg-emerald-500/20 rounded-full flex items-center justify-center">
            <Star class="w-4 h-4 text-emerald-400" />
          </div>
          <span class="text-sm md:text-base">50k+ zadowolonych klientów</span>
        </div>
        <div class="flex items-center gap-3 text-white">
          <div class="w-8 h-8 bg-emerald-500/20 rounded-full flex items-center justify-center">
            <Clock class="w-4 h-4 text-emerald-400" />
          </div>
          <span class="text-sm md:text-base">Dostępność 24/7</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Calendar, Shield, Star, Clock } from 'lucide-vue-next'
</script>

