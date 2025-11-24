<template>
  <section class="py-20 bg-gradient-to-br from-emerald-500 to-emerald-600">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
      <h2 class="text-4xl md:text-5xl text-white mb-6">
        Gotowy na przygodę?
      </h2>
      <p class="text-white/90 text-xl max-w-3xl mx-auto mb-8">
        Szeroka oferta samochodów, w tym elektrycznych i luksusowych. Wypożyczalnia dopasowana do 
        Twoich potrzeb.
      </p>

      <!-- Features -->
      <div class="flex flex-wrap items-center justify-center gap-6 mb-10 text-white">
        <div class="flex items-center gap-2">
          <CheckCircle class="w-5 h-5" />
          <span>Nieograniczony przebieg</span>
        </div>
        <div class="flex items-center gap-2">
          <CheckCircle class="w-5 h-5" />
          <span>Pełne ubezpieczenie</span>
        </div>
        <div class="flex items-center gap-2">
          <CheckCircle class="w-5 h-5" />
          <span>Wsparcie 24/7</span>
        </div>
        <div class="flex items-center gap-2">
          <CheckCircle class="w-5 h-5" />
          <span>Odbiór na lotnisku</span>
        </div>
      </div>

      <!-- CTA Button -->
      <button class="bg-white text-emerald-600 px-10 py-4 rounded-lg hover:bg-gray-100 transition-colors text-lg">
        Zarezerwuj online już teraz
      </button>
    </div>
  </section>
</template>

<script setup>
import { CheckCircle } from 'lucide-vue-next'
</script>

