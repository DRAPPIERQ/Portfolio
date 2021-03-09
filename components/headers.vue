<template>
  <div class="h-12 flex justify-between">
    <div class="mx-2 my-1 flex-row text-2xl">
      <h1 class="text-grey-800 dark:text-white font-bold">DRAPPIER Quentin</h1>
    </div>
    <div id="darkMode" class="mx-2 my-2 flex flex-row align-middle">
      <icons
        icon="sun"
        :outline="isDark"
        class="fill-current w-6 h-6 text-orange-500 dark:text-blue-500"
      />
      <div class="relative inline-block select-none mx-2 my-1">
        <input
          type="checkbox"
          name="toggleDarkMode"
          id="toggleDarkMode"
          v-model="isDark"
          class="transition-transform transform translate-x-0 duration-500 theme-switch absolute block w-4 h-4 rounded-full outline-none bg-orange-200 dark:bg-blue-200 appearance-none cursor-pointer"
        />
        <label
          for="toggleDarkMode"
          class="theme-switch-label block overflow-hidden w-8 h-4 rounded-full bg-orange-500 cursor-pointer"
        />
      </div>
      <icons
        icon="moon"
        :outline="!isDark"
        class="fill-current w-4 h-4 my-1 mx-1 text-orange-500 dark:text-blue-500"
      />
    </div>
  </div>
</template>

<script>
import icons from './icons.vue'
export default {
  components: { icons },
  data: () => {
    return {
      isDark: false,
    }
  },
  watch: {
    isDark: (newValue, oldValue) => {
      if (newValue && newValue != oldValue) {
        localStorage.setItem('theme', 'dark')
        document.documentElement.classList.add('dark-mode')
      } else {
        localStorage.setItem('theme', 'light')
        document.documentElement.classList.remove('dark-mode')
      }
    },
  },
  mounted() {
    if (
      localStorage.theme === 'dark' ||
      (!('theme' in localStorage) &&
        window.matchMedia('(prefers-color-scheme: dark)').matches)
    ) {
      document.documentElement.classList.add('dark-mode')
      this.isDark = true
    } else {
      document.documentElement.classList.remove('dark-mode')
      this.isDark = false
    }
  },
}
</script>

<style>
.theme-switch:checked {
  @apply transition-transform;
  @apply transform;
  @apply translate-x-4;
  @apply duration-500;
}
.theme-switch:checked + .theme-switch-label {
  @apply bg-blue-500;
}
</style>
