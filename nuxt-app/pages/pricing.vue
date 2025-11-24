<template>
  <div class="bg-white">
    <!-- Hero section -->
    <section class="relative h-[400px] flex items-center justify-center overflow-hidden">
      <div class="absolute inset-0">
        <img
          src="https://images.unsplash.com/photo-1563013544-824ae1b704d3?w=1920&q=80"
          alt="Pricing"
          class="w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-gray-900/60"></div>
      </div>
      <div class="relative z-10 text-center text-white">
        <h1 class="text-5xl md:text-6xl mb-4">Cennik</h1>
        <p class="text-xl max-w-2xl mx-auto px-4">
          Przejrzyste ceny bez ukrytych kosztów
        </p>
      </div>
    </section>

    <!-- Quick pricing cards -->
    <section class="py-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid md:grid-cols-3 gap-8 mb-16">
        <div class="bg-white rounded-2xl p-8 border-2 border-gray-200">
          <h3 class="text-2xl mb-2">Ekonomiczne</h3>
          <p class="text-gray-600 mb-6">Dla oszczędnych</p>
          <div class="text-5xl text-emerald-600 mb-2">150 zł</div>
          <div class="text-gray-500 mb-6">za dzień wynajmu</div>
          <button class="w-full bg-emerald-500 text-white py-3 rounded-lg hover:bg-emerald-600 transition-colors">
            Zarezerwuj
          </button>
        </div>

        <div class="bg-emerald-500 text-white rounded-2xl p-8 transform scale-105 shadow-xl relative">
          <div class="absolute -top-4 left-1/2 -translate-x-1/2 bg-white text-emerald-600 px-4 py-1 rounded-full text-sm">
            Najpopularniejsze
          </div>
          <h3 class="text-2xl mb-2">Premium</h3>
          <p class="text-white/80 mb-6">Komfort i styl</p>
          <div class="text-5xl mb-2">350 zł</div>
          <div class="text-white/80 mb-6">za dzień wynajmu</div>
          <button class="w-full bg-white text-emerald-600 py-3 rounded-lg hover:bg-gray-100 transition-colors">
            Zarezerwuj
          </button>
        </div>

        <div class="bg-white rounded-2xl p-8 border-2 border-gray-200">
          <h3 class="text-2xl mb-2">Luksusowe</h3>
          <p class="text-gray-600 mb-6">Najwyższa jakość</p>
          <div class="text-5xl text-emerald-600 mb-2">750 zł</div>
          <div class="text-gray-500 mb-6">za dzień wynajmu</div>
          <button class="w-full bg-emerald-500 text-white py-3 rounded-lg hover:bg-emerald-600 transition-colors">
            Zarezerwuj
          </button>
        </div>
      </div>

      <!-- Detailed comparison table -->
      <div class="mb-16">
        <h2 class="text-3xl mb-8 text-center">Szczegółowe porównanie</h2>
        <div class="overflow-x-auto">
          <table class="w-full border-collapse">
            <thead>
              <tr class="bg-gray-50">
                <th class="text-left p-4 border-b-2 border-gray-200">Funkcja</th>
                <th class="text-center p-4 border-b-2 border-gray-200">Ekonomiczne</th>
                <th class="text-center p-4 border-b-2 border-gray-200 bg-emerald-50">Premium</th>
                <th class="text-center p-4 border-b-2 border-gray-200">Luksusowe</th>
              </tr>
            </thead>
            <tbody>
              <tr
                v-for="(row, index) in pricingTable"
                :key="index"
                class="hover:bg-gray-50"
              >
                <td class="p-4 border-b border-gray-200">{{ row.feature }}</td>
                <td class="p-4 border-b border-gray-200 text-center">
                  <Check v-if="row.economy === true" class="w-5 h-5 text-emerald-500 mx-auto" />
                  <X v-else-if="row.economy === false" class="w-5 h-5 text-gray-300 mx-auto" />
                  <span v-else class="text-sm text-gray-600">{{ row.economy }}</span>
                </td>
                <td class="p-4 border-b border-gray-200 text-center bg-emerald-50/50">
                  <Check v-if="row.premium === true" class="w-5 h-5 text-emerald-500 mx-auto" />
                  <X v-else-if="row.premium === false" class="w-5 h-5 text-gray-300 mx-auto" />
                  <span v-else class="text-sm text-gray-600">{{ row.premium }}</span>
                </td>
                <td class="p-4 border-b border-gray-200 text-center">
                  <Check v-if="row.luxury === true" class="w-5 h-5 text-emerald-500 mx-auto" />
                  <X v-else-if="row.luxury === false" class="w-5 h-5 text-gray-300 mx-auto" />
                  <span v-else class="text-sm text-gray-600">{{ row.luxury }}</span>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>

      <!-- Discounts section -->
      <div class="bg-gray-50 rounded-2xl p-8">
        <h2 class="text-3xl mb-6 text-center">Rabaty długoterminowe</h2>
        <p class="text-gray-600 text-center mb-8">
          Im dłużej wynajmujesz, tym więcej oszczędzasz!
        </p>
        <div class="grid md:grid-cols-3 gap-6">
          <div
            v-for="(discount, index) in discounts"
            :key="index"
            class="bg-white rounded-xl p-6 text-center"
          >
            <div class="text-3xl text-emerald-600 mb-2">{{ discount.discount }}</div>
            <div class="text-gray-600">{{ discount.days }}</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Additional info -->
    <section class="py-20 bg-emerald-500">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-start gap-4 bg-white/10 backdrop-blur-sm rounded-2xl p-8 text-white">
          <Info class="w-6 h-6 flex-shrink-0 mt-1" />
          <div>
            <h3 class="text-xl mb-2">Ważne informacje</h3>
            <ul class="space-y-2 text-white/90">
              <li>• Wszystkie ceny zawierają VAT</li>
              <li>• Minimalny wiek kierowcy: 21 lat, min. 2 lata prawa jazdy</li>
              <li>• Kaucja zwrotna: 500-2000 zł (zależnie od klasy pojazdu)</li>
              <li>• Płatność: gotówka, karta płatnicza, przelew</li>
              <li>• Możliwość wynajmu w jednym mieście, zwrotu w innym (dodatkowa opłata)</li>
              <li>• Rezerwacja online: bez opłat, możliwość anulowania do 24h przed odbiorem</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ section -->
    <section class="py-20 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-3xl mb-8 text-center">Najczęściej zadawane pytania</h2>
      <div class="space-y-4">
        <details
          v-for="(faq, index) in faqs"
          :key="index"
          class="bg-gray-50 rounded-xl p-6 cursor-pointer group"
        >
          <summary class="list-none flex items-center justify-between">
            <span class="text-lg">{{ faq.q }}</span>
            <span class="text-emerald-500 group-open:rotate-180 transition-transform">▼</span>
          </summary>
          <p class="text-gray-600 mt-4">{{ faq.a }}</p>
        </details>
      </div>
    </section>
  </div>
</template>

<script setup>
import { Check, X, Info } from 'lucide-vue-next'

const pricingTable = [
  {
    feature: 'Nieograniczony przebieg',
    economy: true,
    premium: true,
    luxury: true,
  },
  {
    feature: 'Ubezpieczenie OC',
    economy: true,
    premium: true,
    luxury: true,
  },
  {
    feature: 'Ubezpieczenie AC',
    economy: true,
    premium: true,
    luxury: true,
  },
  {
    feature: 'Udział własny w szkodzie',
    economy: '2000 zł',
    premium: '1000 zł',
    luxury: '0 zł',
  },
  {
    feature: 'Pomoc drogowa 24/7',
    economy: true,
    premium: true,
    luxury: true,
  },
  {
    feature: 'Dodatkowy kierowca',
    economy: '50 zł',
    premium: 'Gratis',
    luxury: 'Gratis',
  },
  {
    feature: 'GPS',
    economy: '20 zł/dzień',
    premium: true,
    luxury: true,
  },
  {
    feature: 'Fotelik dziecięcy',
    economy: '20 zł/dzień',
    premium: '20 zł/dzień',
    luxury: 'Gratis',
  },
  {
    feature: 'Dostawa samochodu',
    economy: 'Od 100 zł',
    premium: 'Od 100 zł',
    luxury: 'Gratis',
  },
  {
    feature: 'Mycie samochodu',
    economy: false,
    premium: true,
    luxury: true,
  },
  {
    feature: 'Pełny zbiornik paliwa',
    economy: true,
    premium: true,
    luxury: true,
  },
  {
    feature: 'Priority support',
    economy: false,
    premium: true,
    luxury: true,
  },
]

const discounts = [
  { days: '7-13 dni', discount: '5%' },
  { days: '14-29 dni', discount: '10%' },
  { days: '30+ dni', discount: '15%' },
]

const faqs = [
  {
    q: 'Jak mogę dokonać rezerwacji?',
    a: 'Rezerwacji możesz dokonać przez naszą stronę internetową, telefonicznie lub osobiście w naszych oddziałach.',
  },
  {
    q: 'Jakie dokumenty są potrzebne?',
    a: 'Potrzebujesz ważnego prawa jazdy (min. 2 lata od wydania), dowodu osobistego oraz karty płatniczej do blokady kaucji.',
  },
  {
    q: 'Czy mogę wynająć samochód bez karty kredytowej?',
    a: 'Tak, akceptujemy karty debetowe. Wymagana jest jednak blokada środków jako kaucja zwrotna.',
  },
  {
    q: 'Co się stanie, jeśli spóźnię się ze zwrotem?',
    a: 'Pobieramy opłatę 50 zł za każdą rozpoczętą godzinę opóźnienia. Po 3 godzinach naliczamy pełną dobę wynajmu.',
  },
]

</script>

