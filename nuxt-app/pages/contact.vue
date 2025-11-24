<template>
  <div class="bg-white">
    <!-- Hero section -->
    <section class="relative h-[400px] flex items-center justify-center overflow-hidden">
      <div class="absolute inset-0">
        <img
          src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?w=1920&q=80"
          alt="Contact"
          class="w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-gray-900/60"></div>
      </div>
      <div class="relative z-10 text-center text-white">
        <h1 class="text-5xl md:text-6xl mb-4">Kontakt</h1>
        <p class="text-xl max-w-2xl mx-auto px-4">
          Jesteśmy do Twojej dyspozycji 24/7
        </p>
      </div>
    </section>

    <!-- Contact info cards -->
    <section class="py-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid md:grid-cols-4 gap-6 mb-16">
        <div class="bg-emerald-50 rounded-2xl p-6 text-center">
          <div class="w-12 h-12 bg-emerald-500 rounded-full flex items-center justify-center mx-auto mb-4">
            <Phone class="w-6 h-6 text-white" />
          </div>
          <h3 class="text-lg mb-2">Infolinia</h3>
          <p class="text-gray-600">+48 22 123 45 67</p>
        </div>

        <div class="bg-emerald-50 rounded-2xl p-6 text-center">
          <div class="w-12 h-12 bg-emerald-500 rounded-full flex items-center justify-center mx-auto mb-4">
            <Mail class="w-6 h-6 text-white" />
          </div>
          <h3 class="text-lg mb-2">Email</h3>
          <p class="text-gray-600">kontakt@rentcar.pl</p>
        </div>

        <div class="bg-emerald-50 rounded-2xl p-6 text-center">
          <div class="w-12 h-12 bg-emerald-500 rounded-full flex items-center justify-center mx-auto mb-4">
            <Clock class="w-6 h-6 text-white" />
          </div>
          <h3 class="text-lg mb-2">Godziny</h3>
          <p class="text-gray-600">24/7</p>
        </div>

        <div class="bg-emerald-50 rounded-2xl p-6 text-center">
          <div class="w-12 h-12 bg-emerald-500 rounded-full flex items-center justify-center mx-auto mb-4">
            <MapPin class="w-6 h-6 text-white" />
          </div>
          <h3 class="text-lg mb-2">Lokalizacje</h3>
          <p class="text-gray-600">12 miast w Polsce</p>
        </div>
      </div>

      <!-- Contact form and info -->
      <div class="grid md:grid-cols-2 gap-12 mb-16">
        <!-- Form -->
        <div>
          <h2 class="text-3xl mb-6">Wyślij wiadomość</h2>
          <form @submit.prevent="handleSubmit" class="space-y-4">
            <div>
              <label class="block text-gray-700 mb-2">Imię i nazwisko *</label>
              <input
                type="text"
                required
                v-model="formData.name"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-emerald-500"
                placeholder="Jan Kowalski"
              />
            </div>

            <div>
              <label class="block text-gray-700 mb-2">Email *</label>
              <input
                type="email"
                required
                v-model="formData.email"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-emerald-500"
                placeholder="jan@example.com"
              />
            </div>

            <div>
              <label class="block text-gray-700 mb-2">Telefon</label>
              <input
                type="tel"
                v-model="formData.phone"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-emerald-500"
                placeholder="+48 123 456 789"
              />
            </div>

            <div>
              <label class="block text-gray-700 mb-2">Temat *</label>
              <select
                required
                v-model="formData.subject"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-emerald-500"
              >
                <option value="">Wybierz temat</option>
                <option value="reservation">Rezerwacja</option>
                <option value="question">Pytanie</option>
                <option value="complaint">Reklamacja</option>
                <option value="other">Inne</option>
              </select>
            </div>

            <div>
              <label class="block text-gray-700 mb-2">Wiadomość *</label>
              <textarea
                required
                v-model="formData.message"
                rows="5"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-emerald-500 resize-none"
                placeholder="Twoja wiadomość..."
              />
            </div>

            <button
              type="submit"
              class="w-full bg-emerald-500 text-white px-6 py-3 rounded-lg hover:bg-emerald-600 transition-colors flex items-center justify-center gap-2"
            >
              <Send class="w-5 h-5" />
              Wyślij wiadomość
            </button>
          </form>
        </div>

        <!-- Additional info -->
        <div>
          <h2 class="text-3xl mb-6">Informacje kontaktowe</h2>
          <div class="bg-gray-50 rounded-2xl p-6 mb-6">
            <h3 class="text-xl mb-4">Centrala</h3>
            <div class="space-y-3">
              <div class="flex items-start gap-3">
                <MapPin class="w-5 h-5 text-emerald-500 mt-1" />
                <div>
                  <p class="text-gray-900">ul. Marszałkowska 123</p>
                  <p class="text-gray-600">00-001 Warszawa</p>
                </div>
              </div>
              <div class="flex items-center gap-3">
                <Phone class="w-5 h-5 text-emerald-500" />
                <p class="text-gray-900">+48 22 123 45 67</p>
              </div>
              <div class="flex items-center gap-3">
                <Mail class="w-5 h-5 text-emerald-500" />
                <p class="text-gray-900">kontakt@rentcar.pl</p>
              </div>
              <div class="flex items-center gap-3">
                <Clock class="w-5 h-5 text-emerald-500" />
                <p class="text-gray-900">Dostępni 24/7</p>
              </div>
            </div>
          </div>

          <div class="bg-emerald-50 rounded-2xl p-6">
            <h3 class="text-xl mb-2">Szybki kontakt</h3>
            <p class="text-gray-600 mb-4">
              Potrzebujesz pilnej pomocy? Zadzwoń na naszą infolinię lub napisz na czacie online.
            </p>
            <button class="w-full bg-emerald-500 text-white px-6 py-3 rounded-lg hover:bg-emerald-600 transition-colors">
              Czat online
            </button>
          </div>
        </div>
      </div>

      <!-- Locations -->
      <div>
        <h2 class="text-3xl mb-8 text-center">Nasze oddziały</h2>
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div
            v-for="(location, index) in locations"
            :key="index"
            class="bg-white rounded-2xl p-6 border border-gray-200 hover:border-emerald-500 transition-colors"
          >
            <h3 class="text-xl mb-4">{{ location.city }}</h3>
            <div class="space-y-2 text-sm text-gray-600">
              <div class="flex items-start gap-2">
                <MapPin class="w-4 h-4 text-emerald-500 mt-0.5 flex-shrink-0" />
                <div>
                  <p>{{ location.address }}</p>
                  <p>{{ location.postal }}</p>
                </div>
              </div>
              <div class="flex items-center gap-2">
                <Phone class="w-4 h-4 text-emerald-500 flex-shrink-0" />
                <p>{{ location.phone }}</p>
              </div>
              <div class="flex items-center gap-2">
                <Mail class="w-4 h-4 text-emerald-500 flex-shrink-0" />
                <p>{{ location.email }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Map placeholder -->
    <section class="py-20 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="bg-gray-200 rounded-2xl h-96 flex items-center justify-center">
          <div class="text-center">
            <MapPin class="w-16 h-16 text-gray-400 mx-auto mb-4" />
            <p class="text-gray-600">Tutaj będzie mapa z naszymi lokalizacjami</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { Phone, Mail, MapPin, Clock, Send } from 'lucide-vue-next'

const formData = ref({
  name: '',
  email: '',
  phone: '',
  subject: '',
  message: '',
})

const handleSubmit = () => {
  alert('Dziękujemy za wiadomość! Odpowiemy najszybciej jak to możliwe.')
  formData.value = { name: '', email: '', phone: '', subject: '', message: '' }
}

const locations = [
  {
    city: 'Warszawa',
    address: 'ul. Marszałkowska 123',
    postal: '00-001 Warszawa',
    phone: '+48 22 123 45 67',
    email: 'warszawa@rentcar.pl',
  },
  {
    city: 'Kraków',
    address: 'ul. Floriańska 45',
    postal: '31-019 Kraków',
    phone: '+48 12 234 56 78',
    email: 'krakow@rentcar.pl',
  },
  {
    city: 'Wrocław',
    address: 'ul. Świdnicka 67',
    postal: '50-068 Wrocław',
    phone: '+48 71 345 67 89',
    email: 'wroclaw@rentcar.pl',
  },
  {
    city: 'Gdańsk',
    address: 'ul. Długa 89',
    postal: '80-831 Gdańsk',
    phone: '+48 58 456 78 90',
    email: 'gdansk@rentcar.pl',
  },
  {
    city: 'Poznań',
    address: 'ul. Półwiejska 12',
    postal: '61-888 Poznań',
    phone: '+48 61 567 89 01',
    email: 'poznan@rentcar.pl',
  },
  {
    city: 'Katowice',
    address: 'ul. 3 Maja 34',
    postal: '40-096 Katowice',
    phone: '+48 32 678 90 12',
    email: 'katowice@rentcar.pl',
  },
]
</script>

