<script setup>
import { inject } from 'vue'

const lang = inject('lang')
</script>

<template>
  <section id="expertise" class="py-24 bg-surface-900 border-t border-white/5">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center max-w-3xl mx-auto mb-16 reveal">
        <h2 class="text-sm font-mono text-brand-light mb-3 tracking-widest uppercase">
          {{ lang === 'es' ? 'Áreas de Dominio' : 'Domain Areas' }}
        </h2>
        <h3 class="text-3xl md:text-4xl font-bold text-white mb-6">
          {{ lang === 'es' ? 'Lo que aporto a la mesa' : 'What I bring to the table' }}
        </h3>
        <p class="text-gray-400 text-lg">
          {{ lang === 'es' ? 'Mi enfoque trasciende la simple escritura de código. Analizo, estructuro y optimizo procesos tecnológicos para garantizar operaciones estables y eficientes.' : 'My approach goes beyond simply writing code. I analyze, structure, and optimize technological processes to ensure stable and efficient operations.' }}
        </p>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <!-- Frontend -->
        <div class="glass-card p-8 rounded-xl reveal">
          <div class="w-12 h-12 rounded-lg bg-brand/10 text-brand flex items-center justify-center text-2xl mb-6 border border-brand/20">
            <i class="fab fa-vuejs"></i>
          </div>
          <h4 class="text-xl font-bold text-white mb-3">Frontend Architecture</h4>
          <p class="text-gray-400 text-sm leading-relaxed mb-4">
            {{ lang === 'es' ? 'Diseño de SPAs modernas y escalables. Dominio profundo de Vue.js (2/3), TypeScript y Angular. Creación de librerías de componentes.' : 'Design of modern and scalable SPAs. Deep mastery of Vue.js (2/3), TypeScript, and Angular. Creation of component libraries.' }}
          </p>
        </div>

        <!-- Backend -->
        <div class="glass-card p-8 rounded-xl reveal" style="transition-delay: 0.1s;">
          <div class="w-12 h-12 rounded-lg bg-yellow-500/10 text-yellow-500 flex items-center justify-center text-2xl mb-6 border border-yellow-500/20">
            <i class="fas fa-database"></i>
          </div>
          <h4 class="text-xl font-bold text-white mb-3">Backend & SQL Tuning</h4>
          <p class="text-gray-400 text-sm leading-relaxed mb-4">
            {{ lang === 'es' ? 'Desarrollo de APIs REST robustas con C#/.NET y Node.js. Optimización de consultas SQL y procedimientos almacenados para reducir latencia.' : 'Development of robust REST APIs with C#/.NET and Node.js. Optimization of SQL queries and stored procedures to reduce latency.' }}
          </p>
        </div>

        <!-- Móvil -->
        <div class="glass-card p-8 rounded-xl reveal" style="transition-delay: 0.2s;">
          <div class="w-12 h-12 rounded-lg bg-cyan-500/10 text-cyan-400 flex items-center justify-center text-2xl mb-6 border border-cyan-500/20">
            <i class="fas fa-mobile-alt"></i>
          </div>
          <h4 class="text-xl font-bold text-white mb-3">Multiplataforma</h4>
          <p class="text-gray-400 text-sm leading-relaxed mb-4">
            {{ lang === 'es' ? 'Desarrollo de aplicativos móviles híbridos y nativos utilizando Ionic, .NET MAUI y Blazor, asegurando consistencia en UX/UI.' : 'Development of hybrid and native mobile applications using Ionic, .NET MAUI, and Blazor, ensuring consistency in UX/UI.' }}
          </p>
        </div>
        
        <!-- DevOps -->
        <div class="glass-card p-8 rounded-xl reveal">
          <div class="w-12 h-12 rounded-lg bg-blue-500/10 text-blue-400 flex items-center justify-center text-2xl mb-6 border border-blue-500/20">
            <i class="fas fa-server"></i>
          </div>
          <h4 class="text-xl font-bold text-white mb-3">DevOps & Operaciones</h4>
          <p class="text-gray-400 text-sm leading-relaxed mb-4">
            {{ lang === 'es' ? 'Implementación de estrategias para automatizar procesos. Gestión de CI/CD, despliegues continuos y mantenimiento de infraestructuras críticas.' : 'Implementation of strategies to automate processes. CI/CD management, continuous deployments, and maintenance of critical infrastructures.' }}
          </p>
        </div>

        <!-- Soporte -->
        <div class="glass-card p-8 rounded-xl reveal" style="transition-delay: 0.1s;">
          <div class="w-12 h-12 rounded-lg bg-green-500/10 text-green-400 flex items-center justify-center text-2xl mb-6 border border-green-500/20">
            <i class="fas fa-bug-slash"></i>
          </div>
          <h4 class="text-xl font-bold text-white mb-3">Soporte L1/L2 & QA</h4>
          <p class="text-gray-400 text-sm leading-relaxed mb-4">
            {{ lang === 'es' ? 'Resolución proactiva de incidencias. Mitigación de bugs complejos en entornos de producción, QA y Hotfix. Monitoreo y estabilidad del sistema.' : 'Proactive incident resolution. Mitigation of complex bugs in production, QA, and Hotfix environments. Monitoring and system stability.' }}
          </p>
        </div>

        <!-- IA -->
        <div class="glass-card p-8 rounded-xl reveal" style="transition-delay: 0.2s;">
          <div class="w-12 h-12 rounded-lg bg-purple-500/10 text-purple-400 flex items-center justify-center text-2xl mb-6 border border-purple-500/20">
            <i class="fas fa-brain"></i>
          </div>
          <h4 class="text-xl font-bold text-white mb-3">IA & Automatización</h4>
          <p class="text-gray-400 text-sm leading-relaxed mb-4">
            {{ lang === 'es' ? 'Uso estratégico de IA como apoyo en la investigación y mejora de procesos. Reducción de tareas manuales mediante scripts y automatizaciones.' : 'Strategic use of AI to support research and process improvement. Reduction of manual tasks through scripts and automations.' }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>