<template>
  <section class="py-20 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section header -->
      <div class="text-center mb-12">
        <h2 class="text-4xl md:text-5xl mb-4">Cennik</h2>
        <p class="text-gray-600 text-lg">
          Przejrzyste ceny bez ukrytych kosztów
        </p>
      </div>

      <!-- Pricing cards -->
      <div class="grid md:grid-cols-3 gap-8">
        <div
          v-for="(plan, index) in plans"
          :key="index"
          :class="[
            'rounded-2xl p-8',
            plan.popular
              ? 'bg-emerald-500 text-white shadow-xl scale-105 relative'
              : 'bg-white text-gray-900 border-2 border-gray-100'
          ]"
        >
          <!-- Popular badge -->
          <div v-if="plan.popular" class="absolute -top-4 left-1/2 -translate-x-1/2 bg-white text-emerald-600 px-4 py-1 rounded-full text-sm whitespace-nowrap">
            {{ plan.popularLabel }}
          </div>

          <!-- Plan name -->
          <div class="text-center mb-8">
            <h3 :class="['text-2xl mb-1', plan.popular ? 'text-white' : 'text-gray-900']">
              {{ plan.name }}
            </h3>
            <p :class="['text-sm', plan.popular ? 'text-white/80' : 'text-gray-500']">
              {{ plan.subtitle }}
            </p>
          </div>

          <!-- Price -->
          <div class="text-center mb-8">
            <div class="flex items-baseline justify-center">
              <span class="text-5xl">{{ plan.price }} zł</span>
              <span :class="['text-lg ml-1', plan.popular ? 'text-white/80' : 'text-gray-500']">
                {{ plan.period }}
              </span>
            </div>
          </div>

          <!-- Features -->
          <ul class="space-y-3 mb-8">
            <li v-for="(feature, featureIndex) in plan.features" :key="featureIndex" class="flex items-start gap-3">
              <Check :class="['w-5 h-5 flex-shrink-0 mt-0.5', plan.popular ? 'text-white' : 'text-emerald-500']" />
              <span :class="plan.popular ? 'text-white' : 'text-gray-600'">
                {{ feature }}
              </span>
            </li>
          </ul>

          <!-- CTA Button -->
          <button
            :class="[
              'w-full py-3 rounded-lg transition-colors',
              plan.popular
                ? 'bg-white text-emerald-600 hover:bg-gray-100'
                : 'bg-emerald-500 text-white hover:bg-emerald-600'
            ]"
          >
            Wybierz plan
          </button>
        </div>
      </div>

      <!-- Additional info -->
      <div class="mt-12 text-center">
        <p class="text-gray-600">
          * Ceny mogą się różnić w zależności od sezonu i dostępności. Rabaty dostępne przy wynajmie 
          powyżej 7 dni.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Check } from 'lucide-vue-next'

const plans = [
  {
    name: 'Klasa Ekonomiczna',
    subtitle: 'Idealne na co dzień',
    price: '150',
    period: '/dzień',
    popular: false,
    features: [
      'Nieograniczony przebieg',
      'Ubezpieczenie OC i AC',
      'Podstawowa asystencja',
      'Modele: Skoda Fabia, VW Polo',
    ],
  },
  {
    name: 'Klasa Premium',
    subtitle: 'Komfort i styl',
    price: '350',
    period: '/dzień',
    popular: true,
    popularLabel: 'Najpopularniejsza',
    features: [
      'Nieograniczony przebieg',
      'Pełne ubezpieczenie',
      '24/7 Premium asystencja',
      'GPS i wyposażenie premium',
      'Modele: BMW 5, Audi A6, Tesla',
    ],
  },
  {
    name: 'Klasa Luksusowa',
    subtitle: 'Najwyższa jakość',
    price: '750',
    period: '/dzień',
    popular: false,
    features: [
      'Nieograniczony przebieg',
      'Pełne ubezpieczenie VIP',
      'Dedykowany concierge 24/7',
      'Dostawa pod wskazany adres',
      'Modele: Mercedes S, Porsche',
    ],
  },
]
</script>

