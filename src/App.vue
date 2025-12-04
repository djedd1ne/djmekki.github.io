<template>
  <div class="bg-slate-900 text-white">

    <!-- INTRO ANIMATION -->
    <div v-if="showIntro" class="flex items-center justify-center h-screen bg-black">
      <h1 class="text-6xl font-black tracking-wider opacity-0 animate-fade-slide text-cyan-400">
        {{ name }}
      </h1>
    </div>

    <!-- MAIN WEBSITE -->
    <div v-else>

      <!-- NAVBAR -->
      <header class="fixed top-0 left-0 w-full bg-slate-900/90 backdrop-blur-lg border-b border-slate-800 z-50">
        <div class="max-w-6xl mx-auto flex justify-between items-center px-6 py-5">

          <span class="text-2xl font-black text-cyan-400 tracking-wide">
            DJMEKKI
          </span>

          <!-- Desktop -->
          <nav class="hidden md:flex gap-8 font-semibold text-slate-300">
            <a href="#about" class="hover:text-cyan-400 transition">About</a>
            <a href="#projects" class="hover:text-cyan-400 transition">Projects</a>
            <a href="#skills" class="hover:text-cyan-400 transition">Skills</a>
            <a href="#experience" class="hover:text-cyan-400 transition">Experience</a>
            <a href="#contact" class="hover:text-cyan-400 transition">Contact</a>
          </nav>

          <!-- Mobile button -->
          <button @click="menuOpen = !menuOpen" class="md:hidden text-slate-300">
            <svg v-if="!menuOpen" class="h-8 w-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
            </svg>
            <svg v-else class="h-8 w-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
            </svg>
          </button>
        </div>

        <!-- Mobile dropdown -->
        <div v-if="menuOpen" class="md:hidden bg-slate-800 border-t border-slate-700">
          <nav class="flex flex-col px-6 py-4 space-y-4 text-lg font-semibold text-slate-300">
            <a href="#about" @click="closeMenu" class="hover:text-cyan-400">About</a>
            <a href="#projects" @click="closeMenu" class="hover:text-cyan-400">Projects</a>
            <a href="#skills" @click="closeMenu" class="hover:text-cyan-400">Skills</a>
            <a href="#experience" @click="closeMenu" class="hover:text-cyan-400">Experience</a>
            <a href="#contact" @click="closeMenu" class="hover:text-cyan-400">Contact</a>
          </nav>
        </div>
      </header>

      <!-- SECTIONS -->
      <main class="pt-28">

        <!-- ABOUT -->
        <section id="about" class="py-28 text-center max-w-4xl mx-auto px-6">
          <img src="@/assets/profile.jpg"
            class="w-44 h-44 rounded-full mx-auto shadow-2xl ring-4 ring-cyan-500 mb-8 opacity-0 animate-pop-in object-cover"/>

          <h1 class="text-5xl font-black text-white mb-3">
            {{ name }}
          </h1>

          <h2 class="text-xl font-bold text-cyan-400 uppercase tracking-widest mb-6">
            Software Engineer
          </h2>

          <p class="text-slate-400 text-lg leading-relaxed max-w-2xl mx-auto">
            I architect backend systems, automate cloud infrastructure, and build high‑performance applications. Clean code. Scalable solutions.
          </p>
        </section>

        <!-- PROJECTS -->
        <section id="projects" class="py-28 bg-slate-800 text-center px-6">
          <h2 class="text-4xl font-black text-white mb-8">Projects</h2>

          <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8 max-w-5xl mx-auto">
            <div class="p-6 bg-slate-900 rounded-lg border border-slate-700 hover:border-cyan-500 transition shadow-lg">
              <h3 class="text-xl font-bold text-cyan-400 mb-2">Project One</h3>
              <p class="text-slate-400">Cloud automation pipeline built with Terraform and AWS.</p>
            </div>

            <div class="p-6 bg-slate-900 rounded-lg border border-slate-700 hover:border-cyan-500 transition shadow-lg">
              <h3 class="text-xl font-bold text-cyan-400 mb-2">Project Two</h3>
              <p class="text-slate-400">RESTful API backend using Node.js and PostgreSQL.</p>
            </div>

            <div class="p-6 bg-slate-900 rounded-lg border border-slate-700 hover:border-cyan-500 transition shadow-lg">
              <h3 class="text-xl font-bold text-cyan-400 mb-2">Project Three</h3>
              <p class="text-slate-400">Dockerized microservices with CI/CD integration.</p>
            </div>
          </div>
        </section>

        <!-- SKILLS -->
        <section id="skills" class="py-28 text-center px-6">
          <h2 class="text-4xl font-black text-white mb-10">Skills</h2>

          <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6 max-w-5xl mx-auto">
            <div class="p-6 bg-slate-800 rounded-lg border border-slate-700 hover:border-cyan-500 transition">
              <h3 class="text-lg font-bold text-cyan-400 mb-2">Backend</h3>
              <p class="text-slate-400">Node.js, Python, Go</p>
            </div>

            <div class="p-6 bg-slate-800 rounded-lg border border-slate-700 hover:border-cyan-500 transition">
              <h3 class="text-lg font-bold text-cyan-400 mb-2">Cloud</h3>
              <p class="text-slate-400">AWS, GCP, Docker, K8s</p>
            </div>

            <div class="p-6 bg-slate-800 rounded-lg border border-slate-700 hover:border-cyan-500 transition">
              <h3 class="text-lg font-bold text-cyan-400 mb-2">Databases</h3>
              <p class="text-slate-400">PostgreSQL, MongoDB, Redis</p>
            </div>

            <div class="p-6 bg-slate-800 rounded-lg border border-slate-700 hover:border-cyan-500 transition">
              <h3 class="text-lg font-bold text-cyan-400 mb-2">DevOps</h3>
              <p class="text-slate-400">CI/CD, Terraform, Linux</p>
            </div>
          </div>
        </section>

        <!-- EXPERIENCE -->
        <section id="experience" class="py-28 bg-slate-800 text-center px-6">
          <h2 class="text-4xl font-black text-white mb-10">Experience</h2>

          <div class="max-w-3xl mx-auto text-left space-y-8">
            <div class="border-l-4 border-cyan-500 pl-6">
              <h3 class="text-xl font-bold text-white">Software Engineer</h3>
              <p class="text-cyan-400 text-sm uppercase tracking-wide mb-2">Company Name · 2022 – Present</p>
              <p class="text-slate-400">Built scalable backend services and automated cloud infrastructure.</p>
            </div>

            <div class="border-l-4 border-cyan-500 pl-6">
              <h3 class="text-xl font-bold text-white">Junior Developer</h3>
              <p class="text-cyan-400 text-sm uppercase tracking-wide mb-2">Company Name · 2020 – 2022</p>
              <p class="text-slate-400">Developed APIs and maintained database systems.</p>
            </div>
          </div>
        </section>

        <!-- CONTACT -->
        <section id="contact" class="py-28 text-center px-6">
          <h2 class="text-4xl font-black text-white mb-8">Contact</h2>

          <p class="text-slate-400 text-lg mb-6">
            Open for opportunities. Let's build something great.
          </p>

          <a href="mailto:your@email.com"
            class="inline-block px-8 py-4 bg-cyan-500 text-slate-900 font-bold rounded-lg hover:bg-cyan-400 transition shadow-lg">
            your@email.com
          </a>
        </section>

        <!-- FOOTER -->
        <footer class="py-8 bg-slate-950 text-center text-slate-500 text-sm">
          © 2025 Djallal Eddine · All rights reserved
        </footer>

      </main>

    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue"

const name = "Djallal Eddine"
const showIntro = ref(true)
const menuOpen = ref(false)

onMounted(() => {
  setTimeout(() => { showIntro.value = false }, 1700)
})

const closeMenu = () => (menuOpen.value = false)
</script>

<style>
html { scroll-behavior: smooth; }

@keyframes fade-slide {
  0% { opacity: 0; transform: translateY(30px); }
  100% { opacity: 1; transform: translateY(0); }
}
.animate-fade-slide {
  animation: fade-slide 1s ease-out forwards;
}

@keyframes pop-in {
  0% { opacity: 0; transform: scale(0.8); }
  100% { opacity: 1; transform: scale(1); }
}
.animate-pop-in {
  animation: pop-in 0.8s ease-out forwards;
}
</style>