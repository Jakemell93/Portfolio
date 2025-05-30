<template>
  <nav class="fixed top-0 left-0 w-full bg-white dark:bg-gray-900 backdrop-blur-md z-50">
    <div class="max-w-7xl mx-auto flex items-center justify-between px-6 py-4">
      <!-- Logo / Brand -->
      <div class="text-2xl font-extrabold text-indigo-600 dark:text-indigo-400">
        MyPortfolio
      </div>

      <!-- Desktop links -->
      <ul class="hidden md:flex items-center space-x-6">
        <li v-for="(item, i) in links" :key="i">
          <RouterLink
            :to="item.to"
            class="text-gray-700 dark:text-gray-300 hover:text-indigo-600 dark:hover:text-indigo-400 px-2 py-1 rounded-md transition"
            :class="{
              'text-indigo-600 dark:text-indigo-400 font-semibold underline decoration-2': isActive(item.to)
            }"
          >
            {{ item.label }}
          </RouterLink>
        </li>
      </ul>

      <!-- Mobile hamburger button -->
      <button
        @click="open = !open"
        class="md:hidden p-2 rounded-md text-gray-700 dark:text-gray-300 hover:bg-gray-200 dark:hover:bg-gray-800 transition"
        aria-label="Toggle menu"
      >
        <!-- switched to Bars3Icon and XMarkIcon -->
        <component :is="open ? XMarkIcon : Bars3Icon" class="w-6 h-6" />
      </button>
    </div>

    <!-- Mobile menu panel -->
    <transition name="fade">
      <div
        v-if="open"
        class="md:hidden bg-white dark:bg-gray-900 border-t border-gray-200 dark:border-gray-800"
      >
        <ul class="flex flex-col space-y-2 px-6 py-4">
          <li v-for="(item, i) in links" :key="i">
            <RouterLink
              :to="item.to"
              @click="open = false"
              class="block text-gray-700 dark:text-gray-300 hover:text-indigo-600 dark:hover:text-indigo-400 px-2 py-2 rounded-md transition"
              :class="{ 'font-semibold': isActive(item.to) }"
            >
              {{ item.label }}
            </RouterLink>
          </li>
        </ul>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
import { useRoute } from 'vue-router'
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline' // updated imports

const open = ref(false)
const route = useRoute()

const links = [
  { label: 'Home',     to: '/' },
  { label: 'About',    to: '/about' },
  { label: 'Projects', to: '/projects' },
  { label: 'Contact',  to: '/contact' },
]

function isActive(path) {
  return route.path === path
}
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
