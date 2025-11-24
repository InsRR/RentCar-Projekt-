<template>
  <section class="py-20 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section header -->
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl mb-4">Dlaczego my?</h2>
        <p class="text-gray-600 text-lg max-w-2xl mx-auto">
          Profesjonalne usługi i najwyższe standardy obsługi klienta
        </p>
      </div>

      <!-- Features grid -->
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div
          v-for="(feature, index) in features"
          :key="index"
          class="flex gap-4 p-6 rounded-xl hover:bg-gray-50 transition-colors"
        >
          <div class="flex-shrink-0">
            <div class="w-12 h-12 bg-emerald-100 rounded-xl flex items-center justify-center">
              <component :is="feature.icon" class="w-6 h-6 text-emerald-600" />
            </div>
          </div>
          <div>
            <h3 class="text-xl mb-2">{{ feature.title }}</h3>
            <p class="text-gray-600">{{ feature.description }}</p>
          </div>
        </div>
      </div>

      <!-- CTA -->
      <div class="mt-16 text-center">
        <button class="bg-emerald-500 text-white px-8 py-4 rounded-lg hover:bg-emerald-600 transition-colors inline-flex items-center gap-2">
          Zarezerwuj swój samochód już dziś
          <ArrowRight class="w-5 h-5" />
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Shield, Clock, CreditCard, MapPin, Headphones, ThumbsUp, ArrowRight } from 'lucide-vue-next'

const features = [
  {
    icon: Shield,
    title: 'Pełne ubezpieczenie',
    description: 'Wszystkie pojazdy objęte kompleksowym ubezpieczeniem OC i AC',
  },
  {
    icon: Clock,
    title: 'Dostępność 24/7',
    description: 'Odbiór i zwrot samochodu w każdej porze dnia i nocy',
  },
  {
    icon: CreditCard,
    title: 'Elastyczne płatności',
    description: 'Różne formy płatności i możliwość rozliczenia fakturą',
  },
  {
    icon: MapPin,
    title: 'Wiele lokalizacji',
    description: 'Oddziały w największych miastach Polski i na lotniskach',
  },
  {
    icon: Headphones,
    title: 'Wsparcie klienta',
    description: 'Dedykowana infolinia i pomoc drogowa przez całą dobę',
  },
  {
    icon: ThumbsUp,
    title: 'Bez ukrytych opłat',
    description: 'Przejrzyste ceny i jasne warunki najmu bez niespodzianek',
  },
]
</script>

