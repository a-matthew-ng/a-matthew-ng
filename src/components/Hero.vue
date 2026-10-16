<script setup>
import { inject, ref, onMounted, watch } from "vue";

const lang = inject("lang");
const typewriterText = ref("");

const phrases = {
  es: [
    "> Automatizando despliegues CI/CD.",
    "> Resolviendo bugs críticos L1/L2.",
    "> Integrando IA en flujos de trabajo.",
    "> Construyendo arquitecturas escalables.",
  ],
  en: [
    "> Automating CI/CD deployments.",
    "> Resolving critical L1/L2 bugs.",
    "> Integrating AI into workflows.",
    "> Building scalable architectures.",
  ],
};

let phraseIndex = 0,
  charIndex = 0,
  isDeleting = false,
  timeoutId = null;

const type = () => {
  const currentPhrase = phrases[lang.value][phraseIndex];
  if (isDeleting) {
    typewriterText.value = currentPhrase.substring(0, charIndex - 1);
    charIndex--;
  } else {
    typewriterText.value = currentPhrase.substring(0, charIndex + 1);
    charIndex++;
  }

  let typeSpeed = isDeleting ? 30 : 60;
  if (!isDeleting && charIndex === currentPhrase.length) {
    isDeleting = true;
    typeSpeed = 2000;
  } else if (isDeleting && charIndex === 0) {
    isDeleting = false;
    phraseIndex = (phraseIndex + 1) % phrases[lang.value].length;
    typeSpeed = 500;
  }
  timeoutId = setTimeout(type, typeSpeed);
};

watch(lang, () => {
  clearTimeout(timeoutId);
  phraseIndex = 0;
  charIndex = 0;
  isDeleting = false;
  typewriterText.value = "";
  type();
});

onMounted(() => setTimeout(type, 1000));
</script>

<template>
  <section
    class="relative pt-32 pb-20 lg:pt-48 lg:pb-32 min-h-screen flex items-center"
  >
    <!-- Abstract Background using User Logo -->
    <div
      class="absolute right-0 top-1/2 -translate-y-1/2 w-1/2 opacity-[0.03] pointer-events-none hidden lg:block"
    >
      <img
        src="/transparente.png"
        alt="MW Background"
        class="w-full h-auto object-cover transform translate-x-1/4"
      />
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 w-full">
      <div class="grid lg:grid-cols-12 gap-12 items-center">
        <!-- Text Content -->
        <div class="lg:col-span-7 reveal active">
          <div
            class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-brand-dark/10 border border-brand-light/20 text-brand-light text-xs font-mono font-medium mb-6"
          >
            <span
              class="w-2 h-2 rounded-full bg-green-400 animate-pulse"
            ></span>
            <span>{{
              lang === "es"
                ? "SISTEMAS OPTIMIZADOS & AUTOMATIZADOS"
                : "OPTIMIZED & AUTOMATED SYSTEMS"
            }}</span>
          </div>

          <h1
            class="text-5xl md:text-6xl lg:text-7xl font-bold text-white leading-[1.1] mb-6 tracking-tight"
          >
            <span class="block">{{
              lang === "es" ? "Ingeniería que" : "Engineering that"
            }}</span>
            <span class="text-gradient">{{
              lang === "es" ? "escala procesos." : "scales processes."
            }}</span>
          </h1>

          <div class="h-16 md:h-12 mb-6">
            <p
              class="text-xl md:text-2xl text-gray-300 font-medium font-mono cursor-blink"
            >
              {{ typewriterText }}
            </p>
          </div>

          <p
            class="text-gray-400 text-lg md:text-xl leading-relaxed mb-8 max-w-2xl"
          >
            {{
              lang === "es"
                ? "No solo escribo código; optimizo ecosistemas. Especializado en DevOps, mitigación de bugs complejos, y la integración de IA para automatizar procesos y elevar la calidad del software. Soporte Nivel 1 y 2 con visión estratégica."
                : "I don't just write code; I optimize ecosystems. Specialized in DevOps, complex bug mitigation, and AI integration to automate processes and elevate software quality. L1/L2 Support with a strategic vision."
            }}
          </p>

          <div class="flex flex-wrap gap-4">
            <a
              href="#contact"
              class="px-8 py-4 rounded-md bg-white text-black font-semibold hover:bg-gray-200 transition-colors flex items-center gap-2"
            >
              {{ lang === "es" ? "Integrarme a tu equipo" : "Join your team" }}
              <i class="fas fa-arrow-right"></i>
            </a>
            <a
              href="#expertise"
              class="px-8 py-4 rounded-md border border-gray-700 hover:border-gray-500 text-white font-medium transition-colors"
            >
              {{
                lang === "es" ? "Ver mis capacidades" : "View my capabilities"
              }}
            </a>
          </div>
        </div>

        <!-- Visual Tech Stack / Terminal Mockup -->
        <div class="lg:col-span-5 reveal active" style="transition-delay: 0.2s">
          <div
            class="glass-card rounded-xl overflow-hidden shadow-2xl border-gray-800 relative"
          >
            <!-- Terminal Header -->
            <div
              class="bg-surface-300 px-4 py-3 flex items-center gap-2 border-b border-gray-800"
            >
              <div class="w-3 h-3 rounded-full bg-red-500/80"></div>
              <div class="w-3 h-3 rounded-full bg-yellow-500/80"></div>
              <div class="w-3 h-3 rounded-full bg-green-500/80"></div>
              <span class="ml-4 text-xs font-mono text-gray-500"
                >matthew@devops: ~</span
              >
            </div>
            <!-- Terminal Body -->
            <div
              class="p-6 font-mono text-sm leading-relaxed bg-surface-900/50"
            >
              <div class="text-gray-400 mb-2">
                > <span class="text-blue-400">systemctl</span> status
                engineer.service
              </div>
              <div class="text-green-400 mb-4">
                ● engineer.service - Full Stack & DevOps Automation
              </div>

              <div class="text-gray-300 pl-4 mb-1">
                <span class="text-purple-400">Loaded:</span> loaded
                (/usr/lib/systemd/matthew)
              </div>
              <div class="text-gray-300 pl-4 mb-4">
                <span class="text-purple-400">Active:</span>
                <span class="text-green-400 font-bold">active (running)</span>
                since Tue 2022-01-01
              </div>

              <div class="text-gray-500 mb-2">// Core competencies loaded</div>
              <div class="grid grid-cols-2 gap-2 pl-4 mb-4">
                <div>
                  <span class="text-yellow-300">[OK]</span> CI/CD Pipelines
                </div>
                <div>
                  <span class="text-yellow-300">[OK]</span> L1/L2 Support
                </div>
                <div>
                  <span class="text-yellow-300">[OK]</span> Bug Mitigation
                </div>
                <div>
                  <span class="text-yellow-300">[OK]</span> AI Integration
                </div>
                <div>
                  <span class="text-yellow-300">[OK]</span> Vue.js / .NET
                </div>
                <div>
                  <span class="text-yellow-300">[OK]</span> SQL Optimization
                </div>
              </div>

              <div class="text-gray-400 animate-pulse">> _</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
