<template>
  <div class="min-h-screen bg-grey-200 dark:bg-grey-900 pb-6">
    <headers class="bg-grey-100 dark:bg-grey-800 mb-6" />
    <cards>
      <div class="inline-flex">
        <icons
          icon="mobile-app"
          class="fill-current w-6 h-6 text-orange-500 dark:text-blue-500 font-medium"
        />
        <h1 class="text-orange-500 dark:text-blue-500 font-medium text-xl px-2">
          Applications & APIs
        </h1>
      </div>
      <p class="text-grey-900 dark:text-grey-100">
        Je travaille au sein de l’Agence Cube, à la Roche sur Yon en tant que
        Développeur FullStack.
      </p>
    </cards>
    <cards>
      <div class="md:flex">
        <experiencies class="w-full md:w-1/2" />
        <formations class="w-full mt-12 md:w-1/2 md:mt-0" />
      </div>
    </cards>
    <cards>
      <abilities />
    </cards>
  </div>
</template>

<script>
import cards from '~/layouts/cards.vue'
import headers from '~/components/headers.vue'
import icons from '~/components/icons.vue'
import abilities from '~/components/abilities.vue'
import experiences from '~/components/experiencies.vue'
import formations from '~/components/formations.vue'

export default {
  components: { headers, icons, cards, abilities, experiences, formations },
}
</script>
