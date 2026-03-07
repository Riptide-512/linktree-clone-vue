<script setup>
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue'

const profile = ref({
  name: 'Eric Sepulveda',
  slogan: 'Student and Gamer',
  avatar: 'https://api.dicebear.com/9.x/adventurer-neutral/svg?seed=Felix',
  links: [
    {
      id: 1,
      title: 'GitHub',
      url: 'https://github.com/Riptide-512',
      icon: 'code',
      description: 'Check out my projects and repositories on GitHub.',
    },
    {
      id: 2,
      title: 'LinkedIn',
      url: 'https://www.linkedin.com/in/eric-sepulveda-879ba138a/',
      icon: 'briefcase',
      description: 'Connect with me professionally on LinkedIn.',
    },
    {
      id: 3,
      title: 'Project Bill Splitter',
      url: 'https://expense-splitter-vue.esepulv9.workers.dev/',
      icon: 'project',
      description: 'View my personal projects of a bill splitter.',
    },

    {
      id: 4,
      title: 'Anime Watchlist Randomizer',
      url: 'https://anime-watchlist-randomizer.esepulv9.workers.dev/',
      icon: 'video',
      description: 'Watch some anime with watchlist randomizer.',
    },
  ],
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8">
    <!-- Profile Header-->
    <div class="mb-8 flex flex-col items-center text-center">
      <div
        class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-blue-500 shadow-lg shadow-blue-600/20 sm:h-32 sm:w-32"
      >
        <img
          :src="profile.avatar"
          :alt="profile.name"
          class="h-full w-full object-cover"
        />
      </div>
      <h1 class="mb-2 font-display text-2xl font-bold text-white sm:text-3xl">
        {{ profile.name }}
      </h1>
      <p class="max-w-xs text-gray-300 sm:text-lg">{{ profile.slogan }}</p>
    </div>

    <!-- Links Section -->
    <div class="flex w-full max-w-md flex-col gap-4">
      <LinkCard
        v-for="link in profile.links"
        :key="link.id"
        :title="link.title"
        :url="link.url"
        :description="link.description"
        :icon="link.icon"
      />
    </div>

    <!-- Navigation to info-->
    <RouterLink
      to="/info"
      class="mt-8 text-sm text-gray-400 underline-offset-4 transition-colors duration-200 hover:text-green-400 hover:underline"
      >About me ►
    </RouterLink>
  </main>
</template>
