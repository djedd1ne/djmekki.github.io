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
              <a href="#entrepreneurship" class="hover:text-cyan-400 transition">Entrepreneurship</a>
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
            <a href="#entrepreneurship" @click="closeMenu" class="hover:text-cyan-400">Entrepreneurship</a>
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
          Software Engineer & Entrepreneur
        </h2>

        <p class="text-slate-400 text-lg leading-relaxed max-w-2xl mx-auto">
          Software Engineer with a background in Petroleum Engineering, now building scalable backend systems, cloud infrastructure, and high-performance applications. Experienced in training AI models using RLHF (Reinforcement Learning from Human Feedback). Completed the core curriculum at 42Heilbronn and currently pursuing specialization. Passionate about launching tech startups and turning ideas into impactful products.
        </p>

        <!-- Tech Stack Badges -->
        <div class="flex flex-wrap justify-center gap-3 mt-8">
          <span class="px-4 py-2 bg-gradient-to-r from-slate-800 to-slate-700 text-slate-300 rounded-full text-sm font-medium shadow-md">C/C++</span>
          <span class="px-4 py-2 bg-gradient-to-r from-slate-800 to-slate-700 text-slate-300 rounded-full text-sm font-medium shadow-md">Python</span>
          <span class="px-4 py-2 bg-gradient-to-r from-slate-800 to-slate-700 text-slate-300 rounded-full text-sm font-medium shadow-md">Go</span>
          <span class="px-4 py-2 bg-gradient-to-r from-slate-800 to-slate-700 text-slate-300 rounded-full text-sm font-medium shadow-md">Docker</span>
          <span class="px-4 py-2 bg-gradient-to-r from-slate-800 to-slate-700 text-slate-300 rounded-full text-sm font-medium shadow-md">Kubernetes</span>
          <span class="px-4 py-2 bg-gradient-to-r from-slate-800 to-slate-700 text-slate-300 rounded-full text-sm font-medium shadow-md">AWS</span>
          <span class="px-4 py-2 bg-gradient-to-r from-slate-800 to-slate-700 text-slate-300 rounded-full text-sm font-medium shadow-md">REST API</span>
        </div>

        <!-- Social Links with Icons -->
        <div class="flex justify-center gap-6 mt-10">

          <!-- GitHub -->
          <a href="https://github.com/djedd1ne" target="_blank" class="group flex items-center gap-2 px-5 py-3 bg-slate-800 rounded-full hover:bg-cyan-500 transition shadow-lg">
            <svg class="w-5 h-5 text-cyan-400 group-hover:text-white transition" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 0C5.37 0 0 5.37 0 12c0 5.3 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61-.546-1.385-1.333-1.754-1.333-1.754-1.089-.744.083-.729.083-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.605-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 21.795 24 17.295 24 12c0-6.63-5.37-12-12-12z"/>
            </svg>
            <span class="text-cyan-400 group-hover:text-white font-semibold transition">GitHub</span>
          </a>

          <!-- LinkedIn -->
          <a href="https://www.linkedin.com/in/djallal-me/" target="_blank" class="group flex items-center gap-2 px-5 py-3 bg-slate-800 rounded-full hover:bg-cyan-500 transition shadow-lg">
            <svg class="w-5 h-5 text-cyan-400 group-hover:text-white transition" fill="currentColor" viewBox="0 0 24 24">
              <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
            </svg>
            <span class="text-cyan-400 group-hover:text-white font-semibold transition">LinkedIn</span>
          </a>

        </div>
      </section>

        <!-- PROJECTS -->
        <section id="projects" class="py-28 bg-slate-800 text-center px-6">
          <h2 class="text-4xl font-black text-white mb-8">Projects</h2>
          <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8 max-w-5xl mx-auto">

            <!-- ft_transcendence -->
             <div class="p-6 bg-slate-900 rounded-lg border border-slate-700 hover:border-cyan-500 transition shadow-lg text-left">
              <h3 class="text-xl font-bold text-cyan-400 mb-2">ft_transcendence</h3>
              <p class="text-slate-400">A full-stack single page application featuring real-time 3D multiplayer Pong, live chat, friend system, and 42Auth integration. Built with React, Django, Three.js, and WebSockets.</p>
              <div class="flex flex-wrap gap-2 mt-4">
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">React</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Django</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Three.js</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">WebSockets</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Docker</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">42 Project</span>
              </div>
              <a href="https://github.com/s-sergiu/ft_transcendence" target="_blank" class="block mt-4 text-cyan-400 font-semibold hover:underline">
                View on GitHub →
              </a>
            </div>

            <!-- Coding_Challenge -->
            <div class="p-6 bg-slate-900 rounded-lg border border-slate-700 hover:border-cyan-500 transition shadow-lg text-left">
            <h3 class="text-xl font-bold text-cyan-400 mb-2">Telegram Notification Server</h3>
              <p class="text-slate-400">A Go REST API that sends real-time notifications to Telegram groups via Bot API.</p>
              <div class="flex flex-wrap gap-2 mt-4">
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Go</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">REST API</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Telegram Bot</span>
              </div>
              <a href="https://github.com/djedd1ne/Coding_Challenge" target="_blank" class="text-cyan-400 font-semibold hover:underline">
                View on GitHub →
              </a>
            </div>

            <!-- Weather_Dashboard -->
            <div class="p-6 bg-slate-900 rounded-lg border border-slate-700 hover:border-cyan-500 transition shadow-lg text-left">
              <h3 class="text-xl font-bold text-cyan-400 mb-2">Weather Dashboard</h3>
              <p class="text-slate-400">A modern weather dashboard built with Flask. Displays real-time temperature, humidity, wind speed, and weather conditions for any city worldwide.</p>
              <div class="flex flex-wrap gap-2 mt-4">
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Python</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Flask</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">OpenWeather API</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Responsive</span>
              </div>
              <a href="https://github.com/djedd1ne/Weather_Dashboard" target="_blank" class="block mt-4 text-cyan-400 font-semibold hover:underline">
                View on GitHub →
              </a>
            </div>

            <!-- Project: so_long -->
            <div class="p-6 bg-slate-900 rounded-lg border border-slate-700 hover:border-cyan-500 transition shadow-lg text-left">
              <h3 class="text-xl font-bold text-cyan-400 mb-2">so_long</h3>
              <p class="text-slate-400 mb-4">A 2D tile-based game built in C using MiniLibX. Navigate the map, collect items, and reach the exit. Features sprite rendering and keyboard controls.</p>
              <div class="flex flex-wrap gap-2 mb-4">
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">C</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">MiniLibX</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Makefile</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">42 Project</span>
              </div>
              <a href="https://github.com/djedd1ne/so_long" target="_blank" class="text-cyan-400 font-semibold hover:underline">
                View on GitHub →
              </a>
            </div>

            <!-- Cub3D-->
            <div class="p-6 bg-slate-900 rounded-lg border border-slate-700 hover:border-cyan-500 transition shadow-lg text-left">
              <h3 class="text-xl font-bold text-cyan-400 mb-2">cub3D</h3>
              <p class="text-slate-400">A 3D raycasting game engine inspired by Wolfenstein 3D. Navigate through a maze in first-person view using real-time raycasting rendering.</p>
              <div class="flex flex-wrap gap-2 mt-4">
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">C</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">MiniLibX</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Raycasting</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">42 Project</span>
              </div>
              <a href="https://github.com/s-sergiu/cub3D" target="_blank" class="block mt-4 text-cyan-400 font-semibold hover:underline">
                View on GitHub →
              </a>
            </div>

            <div class="p-6 bg-slate-900 rounded-lg border border-slate-700 hover:border-cyan-500 transition shadow-lg text-left">
              <h3 class="text-xl font-bold text-cyan-400 mb-2">Minishell</h3>
              <p class="text-slate-400">A simplified UNIX shell written in C. Supports pipes, redirections, environment variables, signal handling, and built-in commands like cd, echo, and export.</p>
              <div class="flex flex-wrap gap-2 mt-4">
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">C</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">UNIX</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">Shell</span>
                <span class="px-2 py-1 bg-slate-700 text-xs text-slate-300 rounded">42 Project</span>
              </div>
              <a href="https://github.com/djedd1ne/minishell" target="_blank" class="block mt-4 text-cyan-400 font-semibold hover:underline">
                View on GitHub →
              </a>
            </div>
          </div>
        </section>

        <!-- SKILLS -->
        <section id="skills" class="py-28 text-center px-6">
          <h2 class="text-4xl font-black text-white mb-10">Skills</h2>

          <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6 max-w-5xl mx-auto">

            <div class="p-6 bg-slate-800 rounded-lg border border-slate-700 hover:border-cyan-500 transition">
              <h3 class="text-lg font-bold text-cyan-400 mb-2">Programming</h3>
              <p class="text-slate-400">C/C++, Python, Go, MATLAB</p>
            </div>

            <div class="p-6 bg-slate-800 rounded-lg border border-slate-700 hover:border-cyan-500 transition">
              <h3 class="text-lg font-bold text-cyan-400 mb-2">Web Dev</h3>
              <p class="text-slate-400">HTML, CSS, Bootstrap, Tailwind, JavaScript, Vue.js</p>
            </div>

            <div class="p-6 bg-slate-800 rounded-lg border border-slate-700 hover:border-cyan-500 transition">
              <h3 class="text-lg font-bold text-cyan-400 mb-2">Databases</h3>
              <p class="text-slate-400">PostgreSQL, MariaDB</p>
            </div>

            <div class="p-6 bg-slate-800 rounded-lg border border-slate-700 hover:border-cyan-500 transition">
              <h3 class="text-lg font-bold text-cyan-400 mb-2">Cloud & DevOps</h3>
              <p class="text-slate-400">Docker, Kubernetes, Helm, Github Actions, Azure AKS, Azure Functions, AWS Lambda</p>
            </div>

            <div class="p-6 bg-slate-800 rounded-lg border border-slate-700 hover:border-cyan-500 transition">
              <h3 class="text-lg font-bold text-cyan-400 mb-2">Tools</h3>
              <p class="text-slate-400">Git, Docker,Docker Compose, Kubernetes, Figma, Miro</p>
            </div>

            <div class="p-6 bg-slate-800 rounded-lg border border-slate-700 hover:border-cyan-500 transition">
              <h3 class="text-lg font-bold text-cyan-400 mb-2">Languages</h3>
              <p class="text-slate-400">Arabic (Native), English (C1), French (C1), German (A2)</p>
            </div>

          </div>
        </section>

        <!-- Experiences -->

        <section id="experience" class="py-28 bg-slate-800 text-center px-6">
          <h2 class="text-4xl font-black text-white mb-10">Experience</h2>

          <div class="max-w-3xl mx-auto text-left space-y-8">

            <div class="border-l-4 border-cyan-500 pl-6">
              <h3 class="text-xl font-bold text-white">AI Trainer</h3>
              <p class="text-cyan-400 text-sm uppercase tracking-wide mb-2">Outlier AI · Jun. 2024 – Jun. 2025 · Remote</p>
              <p class="text-slate-400">Crafted and evaluated computer science questions to train and refine AI models using RLHF. Provided human feedback for tasks in French and English. Evaluated and ranked AI-generated code to improve algorithmic performance.</p>
            </div>

            <div class="border-l-4 border-cyan-500 pl-6">
              <h3 class="text-xl font-bold text-white">ESL Mentor</h3>
              <p class="text-cyan-400 text-sm uppercase tracking-wide mb-2">Angloville · Jul. 2021 – Sep. 2021 · Poland</p>
              <p class="text-slate-400">Mentored children aged 12–17 to enhance their English speaking skills. Led a team to achieve a final program presentation.</p>
            </div>

            <div class="border-l-4 border-cyan-500 pl-6">
              <h3 class="text-xl font-bold text-white">Production Intern</h3>
              <p class="text-cyan-400 text-sm uppercase tracking-wide mb-2">Sonatrach · Dec. 2016 – Jan. 2017 · Algeria</p>
              <p class="text-slate-400">Reviewed field operations data and reports. Assisted teams in Production Department at Gassi Touil oil field, one of the leading oil and gas facilities.</p>
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
            contact@djmekki.com
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

const name = "Djallal Eddine Mekki"
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