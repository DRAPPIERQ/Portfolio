<template>
  <div>
    <div class="inline-flex">
      <icons
        icon="ui"
        class="fill-current w-6 h-6 text-orange-500 dark:text-blue-500 font-medium"
      />
      <h1 class="text-orange-500 dark:text-blue-500 font-medium text-xl px-2">
        Mes expériences
      </h1>
    </div>
    <timeline :linesHeight="[6, 12, 5, 2]">
      <cards></cards>
    </timeline>
  </div>
</template>

<script>
import timeline from '~/layouts/timeline.vue'
import cards from '~/layouts/cards.vue'

export default {
  components: { timeline, cards },
}
</script>
