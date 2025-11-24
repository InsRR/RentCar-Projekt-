<template>
  <footer class="bg-gray-900 text-gray-300">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <div class="grid md:grid-cols-4 gap-8 mb-8">
        <!-- Company info -->
        <div>
          <div class="flex items-center gap-3 mb-4">
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
              <div class="text-white">RentCar</div>
              <div class="text-xs text-gray-400">Wypożyczalnia samochodów</div>
            </div>
          </div>
          <p class="text-sm text-gray-400">
            Profesjonalna wypożyczalnia samochodów działająca w całej Polsce od 2010 roku.
          </p>
        </div>

        <!-- Quick links -->
        <div>
          <h4 class="text-white mb-4">Szybkie linki</h4>
          <ul class="space-y-2 text-sm">
            <li>
              <NuxtLink to="/" class="hover:text-emerald-400 transition-colors">
                Strona główna
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/about" class="hover:text-emerald-400 transition-colors">
                O nas
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/offer" class="hover:text-emerald-400 transition-colors">
                Nasza flota
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/pricing" class="hover:text-emerald-400 transition-colors">
                Cennik
              </NuxtLink>
            </li>
            <li>
              <NuxtLink to="/contact" class="hover:text-emerald-400 transition-colors">
                Kontakt
              </NuxtLink>
            </li>
          </ul>
        </div>

        <!-- Services -->
        <div>
          <h4 class="text-white mb-4">Usługi</h4>
          <ul class="space-y-2 text-sm">
            <li>
              <a href="#" class="hover:text-emerald-400 transition-colors">
                Wynajem krótkoterminowy
              </a>
            </li>
            <li>
              <a href="#" class="hover:text-emerald-400 transition-colors">
                Wynajem długoterminowy
              </a>
            </li>
            <li>
              <a href="#" class="hover:text-emerald-400 transition-colors">
                Samochody z kierowcą
              </a>
            </li>
            <li>
              <a href="#" class="hover:text-emerald-400 transition-colors">
                Samochody elektryczne
              </a>
            </li>
            <li>
              <a href="#" class="hover:text-emerald-400 transition-colors">
                Transfer na lotnisko
              </a>
            </li>
          </ul>
        </div>

        <!-- Contact -->
        <div>
          <h4 class="text-white mb-4">Kontakt</h4>
          <ul class="space-y-3 text-sm">
            <li class="flex items-center gap-2">
              <Phone class="w-4 h-4 text-emerald-400" />
              <span>+48 22 123 45 67</span>
            </li>
            <li class="flex items-center gap-2">
              <Mail class="w-4 h-4 text-emerald-400" />
              <span>kontakt@rentcar.pl</span>
            </li>
            <li class="flex items-start gap-2">
              <MapPin class="w-4 h-4 text-emerald-400 mt-1" />
              <span>ul. Przykładowa 123<br />00-001 Warszawa</span>
            </li>
          </ul>

          <!-- Social media -->
          <div class="flex gap-3 mt-4">
            <a
              href="#"
              class="w-8 h-8 bg-gray-800 rounded-full flex items-center justify-center hover:bg-emerald-500 transition-colors"
            >
              <Facebook class="w-4 h-4" />
            </a>
            <a
              href="#"
              class="w-8 h-8 bg-gray-800 rounded-full flex items-center justify-center hover:bg-emerald-500 transition-colors"
            >
              <Instagram class="w-4 h-4" />
            </a>
            <a
              href="#"
              class="w-8 h-8 bg-gray-800 rounded-full flex items-center justify-center hover:bg-emerald-500 transition-colors"
            >
              <Twitter class="w-4 h-4" />
            </a>
          </div>
        </div>
      </div>

      <!-- Bottom bar -->
      <div class="border-t border-gray-800 pt-8 text-center text-sm text-gray-400">
        <p>© 2024 RentCar. Wszelkie prawa zastrzeżone. | Polityka prywatności | Regulamin</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { Phone, Mail, MapPin, Facebook, Instagram, Twitter } from 'lucide-vue-next'
</script>

