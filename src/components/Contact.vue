<script setup>
import { inject } from 'vue'

const lang = inject('lang')
</script>

<template>
  <section id="contact" class="py-32 relative overflow-hidden">
    <div class="absolute inset-0 z-0 flex items-center justify-center opacity-5">
      <img src="/transparente.png" alt="Background Element" class="w-full max-w-4xl object-contain">
    </div>

    <div class="max-w-3xl mx-auto px-4 text-center relative z-10 reveal">
      <div class="mb-8 flex justify-center">
        <img src="/marcaMW1.png" alt="MW Icon" class="w-16 h-16 opacity-90 filter drop-shadow-[0_0_15px_rgba(155,130,214,0.5)]">
      </div>

      <h2 class="text-4xl md:text-5xl font-bold text-white mb-6">
        {{ lang === 'es' ? '¿Buscando eficiencia y calidad?' : 'Looking for efficiency and quality?' }}
      </h2>

      <p class="text-xl text-gray-400 mb-10 leading-relaxed">
        {{ lang === 'es' ? 'Estoy abierto a nuevos retos que busquen mejorar la eficiencia, calidad y desarrollo de sus programas corporativos. Si necesitas un perfil enfocado en soluciones, hablemos.' : "I am open to new challenges aiming to improve efficiency, quality, and development of corporate programs. If you need a solutions-focused profile, let's talk." }}
      </p>

      <div class="flex flex-col sm:flex-row justify-center items-center gap-4">
        <a href="https://wa.me/573054705668?text=Hola%20Matthew,%20vi%20tu%20portafolio%20y%20me%20gustaría%20contactarte." target="_blank" class="px-8 py-4 rounded-md bg-[#25D366] hover:bg-[#128C7E] text-white font-bold transition-all shadow-[0_0_20px_rgba(37,211,102,0.3)] flex items-center justify-center gap-2 text-lg w-full sm:w-auto">
          <i class="fab fa-whatsapp text-xl"></i> WhatsApp
        </a>
        <a href="mailto:matthewalexanderng@gmail.com" class="px-8 py-4 rounded-md bg-brand hover:bg-brand-accent text-white font-bold transition-all shadow-[0_0_20px_rgba(155,130,214,0.3)] flex items-center justify-center gap-2 text-lg w-full sm:w-auto">
          <i class="fas fa-envelope"></i> <span>{{ lang === 'es' ? 'Enviar Correo' : 'Send Email' }}</span>
        </a>
        <a href="https://linkedin.com/in/matthew-a-nuñez-gomez" target="_blank" class="px-8 py-4 rounded-md bg-surface-200 hover:bg-surface-100 border border-gray-700 text-white font-medium transition-all flex items-center justify-center gap-2 text-lg w-full sm:w-auto">
          <i class="fab fa-linkedin text-[#0A66C2]"></i> LinkedIn
        </a>
      </div>
    </div>
  </section>
</template>