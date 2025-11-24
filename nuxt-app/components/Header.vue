<template>
  <header class="bg-white border-b border-gray-200">
    <!-- Top bar -->
    <div class="bg-gray-50 border-b border-gray-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between h-10">
          <div class="flex items-center gap-6">
            <div class="flex items-center gap-2">
              <Phone class="w-4 h-4 text-emerald-500" />
              <span class="text-sm text-gray-600">+48 22 123 45 67</span>
            </div>
            <div class="flex items-center gap-2">
              <Clock class="w-4 h-4 text-emerald-500" />
              <span class="text-sm text-gray-600">Pn-Nd: 24/7</span>
            </div>
          </div>
          <div class="flex items-center gap-2">
            <span class="text-orange-500">⭐</span>
            <span class="text-sm text-gray-600">
              Promocja: -15% na wynajem powyżej 7 dni!
            </span>
          </div>
        </div>
      </div>
    </div>

    <!-- Main navigation -->
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <!-- Logo -->
        <div class="flex items-center gap-3">
          <div class="bg-emerald-500 rounded-lg p-2">
            <svg
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M18 8C18 6.9 17.1 6 16 6H8C6.9 6 6 6.9 6 8V16H18V8Z"
                fill="white"
              />
              <path
                d="M4 16C4 17.1 4.9 18 6 18C7.1 18 8 17.1 8 16H16C16 17.1 16.9 18 18 18C19.1 18 20 17.1 20 16H21V12L18 8H16V16H8V8H6L4 12V16Z"
                fill="white"
              />
            </svg>
          </div>
          <div>
            <div class="font-semibold text-gray-900">RentCar</div>
            <div class="text-xs text-gray-500">Wypożyczalnia samochodów</div>
          </div>
        </div>

        <!-- Navigation menu -->
        <nav class="hidden md:flex items-center gap-8">
          <NuxtLink to="/" class="text-gray-900 hover:text-emerald-500 transition-colors">
            Strona główna
          </NuxtLink>
          <NuxtLink to="/about" class="text-gray-600 hover:text-emerald-500 transition-colors">
            O nas
          </NuxtLink>
          <NuxtLink to="/offer" class="text-gray-600 hover:text-emerald-500 transition-colors">
            Oferta
          </NuxtLink>
          <NuxtLink to="/pricing" class="text-gray-600 hover:text-emerald-500 transition-colors">
            Cennik
          </NuxtLink>
          <NuxtLink to="/contact" class="text-gray-600 hover:text-emerald-500 transition-colors">
            Kontakt
          </NuxtLink>
        </nav>

        <!-- CTA Button -->
        <button class="bg-emerald-500 text-white px-6 py-2.5 rounded-lg hover:bg-emerald-600 transition-colors">
          Rezerwuj online
        </button>
      </div>
    </div>
  </header>
</template>

<script setup>
import { Phone, Clock } from 'lucide-vue-next'
</script>

