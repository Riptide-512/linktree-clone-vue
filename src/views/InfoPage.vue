<script setup>
import { ref } from 'vue'

const bio = ref({
  name: 'Eric Sepulveda',
  avatar: 'https://api.dicebear.com/9.x/adventurer-neutral/svg?seed=Felix',
  about:
    'I am a System Analyst II at UTRGV and Student at South Texas College. I love to play video games, and passionate about learning new techologies.',
  skills: ['JavaScript', 'Vue.js', 'Gaming', 'Cooking', 'Typescript'],
  email: 'esepulv9@southtexascollege.edu',
  location: 'McAllen, Texas',
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:py-12">
    <RouterLink
      to="/"
      class="my-8 self-start text-sm text-gray-400 underline-offset-4 transition-colors duration-200 hover:text-green-400 hover:underline"
    >
      ◄ Back to Links
    </RouterLink>

    <!--Profile Card-->
    <div
      class="w-full max-w-lg rounded-2xl border border-gray-200 bg-gray-800 p-6 shadow-xl shadow-gray-800/50 sm:p-8"
    >
      <!--Header Section-->
      <div class="mb-6 flex flex-col items-center text-center sm:flex-row sm:text-left">
        <div
          class="h-20 w-20 shrink-0 overflow-hidden rounded-full border-4 border-blue-400 sm:mr-6 sm:mb-0"
        >
          <img
            :src="bio.avatar"
            :alt="bio.name"
            class="h-full w-full object-cover"
          />
        </div>
        <div>
          <h1 class="mb-1 font-display text-2xl font-bold text-white">{{ bio.name }}</h1>
          <p class="text-sm text-gray-300">📍{{ bio.location }}</p>
        </div>
      </div>

      <!--About Section-->
      <div class="mb-6">
        <h2 class="mb-3 text-lg font-semibold text-white">About:</h2>
        <p class="leading-relaxed text-gray-300">{{ bio.about }}</p>
      </div>

      <!--Skills Section-->
      <div>
        <h2 class="mb-3 text-lg font-semibold text-white">Skills:</h2>
        <div class="flex flex-wrap gap-2">
          <span
            v-for="skill in bio.skills"
            :key="skill"
            class="rounded-full bg-blue-400 px-3 py-1 text-xs font-medium text-gray-300"
          >
            {{ skill }}
          </span>
        </div>
      </div>

      <!--Contact Section-->
      <div>
        <h2 class="mb-3 text-lg font-semibold text-white">Send Me a Message:</h2>
        <a
          :href="`mailto:${bio.email}`"
          class="group inline-flex items-center gap-2 rounded-xl bg-blue-400 px-6 py-3 font-medium text-white shadow-lg shadow-blue-500/30 transition-all duration-200 hover:scale-105 hover:bg-blue-500 hover:shadow-xl hover:shadow-blue-500/40 active:scale-95"
        >
          <svg
            data-slot="icon"
            fill="none"
            stroke-width="1.5"
            stroke="CurrentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
            aria-hidden="true"
            class="h-5 w-5 transition-transform duration-200 group-hover:rotate-12"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M20 4H4C2.897 4 2 4.897 2 6v12c0 1.103.897 2 2 2h16c1.103 0 2-.897 2-2V6c0-1.103-.897-2-2-2zm0 2l-8 5-8-5h16zm0 12H4V8l8 5 8-5v10z"
            ></path>
          </svg>
          Email Me
        </a>
      </div>
    </div>
  </main>
</template>
