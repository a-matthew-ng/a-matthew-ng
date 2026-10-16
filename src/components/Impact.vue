<script setup>
import { inject } from 'vue'

const lang = inject('lang')
</script>

<template>
  <section id="impact" class="py-24 relative overflow-hidden">
    <div class="absolute right-0 top-0 w-1/3 h-full bg-surface-200 skew-x-12 translate-x-20 z-[-1]"></div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col md:flex-row justify-between items-end mb-16 reveal">
        <div class="max-w-2xl">
          <h2 class="text-3xl md:text-5xl font-bold text-white mb-4">
            {{ lang === 'es' ? 'Historial de Impacto' : 'Track Record of Impact' }}
          </h2>
          <p class="text-gray-400 text-lg">
            {{ lang === 'es' ? 'Resultados medibles y soluciones arquitectónicas implementadas en entornos corporativos de alta exigencia.' : 'Measurable results and architectural solutions implemented in high-demand corporate environments.' }}
          </p>
        </div>
      </div>

      <div class="space-y-8">
        <!-- Logro 1 -->
        <div class="glass-card p-6 md:p-10 rounded-2xl reveal group relative overflow-hidden">
          <div class="absolute top-0 left-0 w-1 h-full bg-green-500 transform origin-top scale-y-0 group-hover:scale-y-100 transition-transform duration-300"></div>
          <div class="grid md:grid-cols-4 gap-6 items-start">
            <div class="md:col-span-1">
              <span class="inline-block px-3 py-1 bg-green-500/10 text-green-400 text-xs font-mono font-bold rounded-full mb-3 uppercase tracking-wider">DevOps & QA</span>
              <h3 class="text-2xl font-bold text-white mb-2">{{ lang === 'es' ? 'Estabilización Core' : 'Core Stabilization' }}</h3>
            </div>
            <div class="md:col-span-3">
              <p class="text-gray-300 mb-4 leading-relaxed">
                {{ lang === 'es' ? 'Lideré la estabilización de módulos críticos de pago y transacciones. Implementé rigurosos procesos de testing funcional y mitigación de bugs en entornos QA y Hotfix, reduciendo la tasa de fallos en producción significativamente.' : 'Led the stabilization of critical payment and transaction modules. Implemented rigorous functional testing and bug mitigation processes in QA and Hotfix environments, significantly reducing the failure rate in production.' }}
              </p>
              <div class="flex flex-wrap gap-2 mt-4">
                <span class="text-xs text-gray-500 bg-surface-900 px-2 py-1 rounded border border-gray-800">L1/L2 Support</span>
                <span class="text-xs text-gray-500 bg-surface-900 px-2 py-1 rounded border border-gray-800">QA Testing</span>
                <span class="text-xs text-gray-500 bg-surface-900 px-2 py-1 rounded border border-gray-800">Bug Mitigation</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Logro 2 -->
        <div class="glass-card p-6 md:p-10 rounded-2xl reveal group relative overflow-hidden">
          <div class="absolute top-0 left-0 w-1 h-full bg-brand transform origin-top scale-y-0 group-hover:scale-y-100 transition-transform duration-300"></div>
          <div class="grid md:grid-cols-4 gap-6 items-start">
            <div class="md:col-span-1">
              <span class="inline-block px-3 py-1 bg-brand/10 text-brand-light text-xs font-mono font-bold rounded-full mb-3 uppercase tracking-wider">Architecture</span>
              <h3 class="text-2xl font-bold text-white mb-2">{{ lang === 'es' ? 'Reducción de Deuda Técnica' : 'Technical Debt Reduction' }}</h3>
            </div>
            <div class="md:col-span-3">
              <p class="text-gray-300 mb-4 leading-relaxed">
                {{ lang === 'es' ? 'Migración de sistemas monolíticos obsoletos (JSP/Java) hacia arquitecturas SPA modernas. Definí estructuras base modulares e implementé librerías de componentes reutilizables, acelerando los tiempos de desarrollo de nuevos features.' : 'Migration of obsolete monolithic systems (JSP/Java) to modern SPA architectures. Defined modular base structures and implemented reusable component libraries, accelerating development times for new features.' }}
              </p>
              <div class="flex flex-wrap gap-2 mt-4">
                <span class="text-xs text-gray-500 bg-surface-900 px-2 py-1 rounded border border-gray-800">Vue 3</span>
                <span class="text-xs text-gray-500 bg-surface-900 px-2 py-1 rounded border border-gray-800">TypeScript</span>
                <span class="text-xs text-gray-500 bg-surface-900 px-2 py-1 rounded border border-gray-800">SPA Architecture</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Logro 3 -->
        <div class="glass-card p-6 md:p-10 rounded-2xl reveal group relative overflow-hidden">
          <div class="absolute top-0 left-0 w-1 h-full bg-blue-500 transform origin-top scale-y-0 group-hover:scale-y-100 transition-transform duration-300"></div>
          <div class="grid md:grid-cols-4 gap-6 items-start">
            <div class="md:col-span-1">
              <span class="inline-block px-3 py-1 bg-blue-500/10 text-blue-400 text-xs font-mono font-bold rounded-full mb-3 uppercase tracking-wider">Performance</span>
              <h3 class="text-2xl font-bold text-white mb-2">{{ lang === 'es' ? 'Optimización Full Stack' : 'Full Stack Optimization' }}</h3>
            </div>
            <div class="md:col-span-3">
              <p class="text-gray-300 mb-4 leading-relaxed">
                {{ lang === 'es' ? 'Aceleración de tiempos de respuesta end-to-end. Reestructuré consultas SQL complejas y procedimientos almacenados en el backend (.NET), mientras optimizaba la gestión de estado y el renderizado en aplicaciones cliente.' : 'Acceleration of end-to-end response times. Restructured complex SQL queries and stored procedures in the backend (.NET), while optimizing state management and rendering in client applications.' }}
              </p>
              <div class="flex flex-wrap gap-2 mt-4">
                <span class="text-xs text-gray-500 bg-surface-900 px-2 py-1 rounded border border-gray-800">C# / .NET</span>
                <span class="text-xs text-gray-500 bg-surface-900 px-2 py-1 rounded border border-gray-800">SQL Tuning</span>
                <span class="text-xs text-gray-500 bg-surface-900 px-2 py-1 rounded border border-gray-800">Performance</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>