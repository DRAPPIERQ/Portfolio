<template>
  <div>
    <div class="inline-flex">
      <icons
        icon="ui"
        class="fill-current w-6 h-6 text-orange-500 dark:text-blue-500 font-medium"
      />
      <h1 class="text-orange-500 dark:text-blue-500 font-medium text-xl px-2">
        Mes compétences
      </h1>
    </div>
  </div>
</template>

<script>
import cards from '~/layouts/cards.vue'

export default {
  components: { cards },
  data: () => {
    return {}
  },
}
</script>
