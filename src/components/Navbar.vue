<script setup>
import { inject, ref, onMounted, onUnmounted } from 'vue'

const lang = inject('lang')
const toggleLang = inject('toggleLang')

const isScrolled = ref(false)
const mobileMenuOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <nav :class="[
    'fixed w-full z-50 transition-all duration-300 glass border-b-0',
    isScrolled ? 'py-2 bg-surface-900/95 shadow-lg' : 'py-4'
  ]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center">
        <!-- Logo -->
        <a href="#" class="flex items-center gap-3 group">
          <img src="/marcaMW.svg" alt="MW Logo" class="h-8 w-auto filter invert opacity-80 group-hover:opacity-100 transition-opacity">
          <span class="font-mono font-bold text-lg tracking-tighter text-white opacity-0 group-hover:opacity-100 transition-opacity duration-300 absolute left-12">NUNEZ</span>
        </a>
        
        <!-- Desktop Menu -->
        <div class="hidden md:flex space-x-8 items-center">
          <a href="#expertise" class="text-sm font-medium text-gray-400 hover:text-white transition-colors tracking-wide">
            {{ lang === 'es' ? 'Experiencia Core' : 'Core Expertise' }}
          </a>
          <a href="#impact" class="text-sm font-medium text-gray-400 hover:text-white transition-colors tracking-wide">
            {{ lang === 'es' ? 'Impacto & Logros' : 'Impact & Achievements' }}
          </a>
          <a href="#philosophy" class="text-sm font-medium text-gray-400 hover:text-white transition-colors tracking-wide">
            {{ lang === 'es' ? 'Filosofía' : 'Philosophy' }}
          </a>
          
          <div class="h-4 w-px bg-gray-700 mx-2"></div>
          
          <!-- Language Toggle Desktop -->
          <button @click="toggleLang" class="flex items-center gap-2 text-sm font-mono text-gray-400 hover:text-brand-light transition-colors">
            <i class="fas fa-globe"></i> <span>{{ lang.toUpperCase() }}</span>
          </button>

          <a href="#contact" class="px-5 py-2 rounded-md bg-white/5 hover:bg-white/10 border border-white/10 text-white text-sm font-medium transition-all backdrop-blur-sm">
            {{ lang === 'es' ? 'Hablemos' : "Let's Talk" }}
          </a>
        </div>

        <!-- Mobile Menu Button -->
        <div class="md:hidden flex items-center gap-4">
          <button @click="toggleLang" class="text-sm font-mono text-gray-400">
            {{ lang.toUpperCase() }}
          </button>
          <button @click="toggleMobileMenu" class="text-gray-300 focus:outline-none">
            <i class="fas fa-bars text-xl"></i>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu Panel -->
    <div v-show="mobileMenuOpen" class="md:hidden absolute w-full glass mt-4 border-t border-white/10">
      <div class="px-4 pt-2 pb-4 space-y-2">
        <a @click="toggleMobileMenu" href="#expertise" class="block px-3 py-2 text-gray-300 hover:text-white rounded-md text-base font-medium">
          {{ lang === 'es' ? 'Experiencia Core' : 'Core Expertise' }}
        </a>
        <a @click="toggleMobileMenu" href="#impact" class="block px-3 py-2 text-gray-300 hover:text-white rounded-md text-base font-medium">
          {{ lang === 'es' ? 'Impacto & Logros' : 'Impact & Achievements' }}
        </a>
        <a @click="toggleMobileMenu" href="#philosophy" class="block px-3 py-2 text-gray-300 hover:text-white rounded-md text-base font-medium">
          {{ lang === 'es' ? 'Filosofía' : 'Philosophy' }}
        </a>
        <a @click="toggleMobileMenu" href="#contact" class="block px-3 py-2 text-brand-light font-medium">
          {{ lang === 'es' ? 'Hablemos' : "Let's Talk" }}
        </a>
      </div>
    </div>
  </nav>
</template>