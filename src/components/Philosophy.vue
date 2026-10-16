<script setup>
import { inject } from "vue";

const lang = inject("lang");
</script>

<template>
  <section
    id="philosophy"
    class="py-20 bg-surface-900 border-y border-white/5 relative"
  >
    <div class="max-w-4xl mx-auto px-4 text-center reveal">
      <i class="fas fa-quote-left text-4xl text-brand-dark/50 mb-6"></i>
      <h2
        class="text-2xl md:text-3xl text-gray-200 font-medium leading-relaxed mb-8"
      >
        {{
          lang === "es"
            ? "Mi valor no reside en la cantidad de líneas de código que escribo, sino en los problemas que evito, los procesos que automatizo y la estabilidad que garantizo en producción."
            : "My value lies not in the amount of code lines I write, but in the problems I avoid, the processes I automate, and the stability I guarantee in production."
        }}
      </h2>
      <p class="text-brand-light font-mono text-sm uppercase tracking-widest">
        — Matthew Nuñez
      </p>
    </div>
  </section>
</template>
