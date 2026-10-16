<script setup>
import { ref, provide, onMounted } from "vue";
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import Expertise from "./components/Expertise.vue";
import Impact from "./components/Impact.vue";
import Philosophy from "./components/Philosophy.vue";
import Contact from "./components/Contact.vue";

// Sistema reactivo de Idioma (Mejorado para Vue)
const lang = ref("es");
const toggleLang = () => {
  lang.value = lang.value === "es" ? "en" : "es";
};

provide("lang", lang);
provide("toggleLang", toggleLang);

// Animación Scroll Reveal centralizada
onMounted(() => {
  const reveal = () => {
    const reveals = document.querySelectorAll(".reveal");
    for (let i = 0; i < reveals.length; i++) {
      if (reveals[i].getBoundingClientRect().top < window.innerHeight - 100) {
        reveals[i].classList.add("active");
      }
    }
  };
  window.addEventListener("scroll", reveal);
  reveal();
});
</script>

<template>
  <div class="fixed inset-0 z-[-1] overflow-hidden pointer-events-none">
    <div
      class="absolute top-0 left-1/4 w-96 h-96 bg-brand-dark/20 rounded-full mix-blend-screen filter blur-[100px] animate-blob"
    ></div>
    <div
      class="absolute top-1/4 right-1/4 w-96 h-96 bg-blue-900/20 rounded-full mix-blend-screen filter blur-[100px] animate-blob animation-delay-2000"
    ></div>
    <div
      class="absolute -bottom-32 left-1/2 w-96 h-96 bg-purple-900/20 rounded-full mix-blend-screen filter blur-[100px] animate-blob animation-delay-4000"
    ></div>
  </div>

  <Navbar />
  <Hero />
  <Expertise />
  <Impact />
  <Philosophy />
  <Contact />

  <!-- Footer y Botón Flotante -->
  <a
    href="https://wa.me/573054705668"
    target="_blank"
    class="fixed bottom-6 right-6 w-14 h-14 bg-[#25D366] text-white rounded-full flex items-center justify-center text-3xl shadow-[0_4px_14px_rgba(37,211,102,0.4)] hover:scale-110 hover:bg-[#128C7E] transition-all duration-300 z-50 group"
  >
    <i class="fab fa-whatsapp"></i>
    <span
      class="absolute right-16 bg-surface-900 text-white text-sm px-3 py-1 rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap border border-white/10 pointer-events-none"
    >
      {{ lang === "es" ? "¡Hablemos!" : "Let's chat!" }}
    </span>
  </a>

  <footer
    class="py-8 border-t border-white/5 bg-surface-900 text-center text-sm text-gray-500 font-mono"
  >
    <p>
      {{
        lang === "es"
          ? "© 2026 Matthew Nuñez. Arquitectura, DevOps & Soluciones."
          : "© 2026 Matthew Nuñez. Architecture, DevOps & Solutions."
      }}
    </p>
  </footer>
</template>
