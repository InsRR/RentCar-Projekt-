<template>
  <section class="py-20 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Section header -->
      <div class="text-center mb-12">
        <h2 class="text-4xl md:text-5xl mb-4">Opinie klientów</h2>
        <p class="text-gray-600 text-lg">
          Zaufało nam ponad 50 000 zadowolonych klientów
        </p>
      </div>

      <!-- Testimonials grid -->
      <div class="grid md:grid-cols-3 gap-8">
        <div
          v-for="(testimonial, index) in testimonials"
          :key="index"
          class="bg-white rounded-2xl p-8 shadow-sm hover:shadow-md transition-shadow relative"
        >
          <!-- Quote icon -->
          <div class="absolute top-6 right-6 opacity-10">
            <Quote class="w-16 h-16 text-emerald-500" />
          </div>

          <!-- Stars -->
          <div class="flex gap-1 mb-4">
            <Star
              v-for="i in testimonial.rating"
              :key="i"
              class="w-5 h-5 fill-emerald-500 text-emerald-500"
            />
          </div>

          <!-- Text -->
          <p class="text-gray-600 mb-6 italic leading-relaxed">
            {{ testimonial.text }}
          </p>

          <!-- Author -->
          <div class="pt-4 border-t border-gray-100">
            <div class="text-gray-900">{{ testimonial.author }}</div>
            <div class="text-gray-500 text-sm">{{ testimonial.position }}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Star, Quote } from 'lucide-vue-next'

const testimonials = [
  {
    rating: 5,
    text: '"Korzystam z usług RentCar od 3 lat. Profesjonalna obsługa, czysty i zadbane samochody. Polecam szczególnie wynajem z kierowcą - zawsze punktualnie i z klasą!"',
    author: 'Anna Kowalska',
    position: 'Przedsiębiorca',
  },
  {
    rating: 5,
    text: '"Wypożyczyłem Teslę Model 3 na urlop - wspaniałe doświadczenie! Samochód jak nowy, obsługa na najwyższym poziomie. RentCar to mój pierwszy wybór przy wynajmie aut."',
    author: 'Michał Nowak',
    position: 'Manager',
  },
  {
    rating: 5,
    text: '"Firma godna polecenia! Rezerwacja online super prosta, samochód gotowy na czas. Nieograniczony przebieg i elastyczne warunki najmu to duży plus. Na pewno wrócę!"',
    author: 'Katarzyna Wiśniewska',
    position: 'Kierownik Działu',
  },
]
</script>

