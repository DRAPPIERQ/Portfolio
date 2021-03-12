<template>
  <div>
    <div class="inline-flex">
      <icons
        icon="ebook"
        class="fill-current w-6 h-6 text-orange-500 dark:text-blue-500 font-medium"
      />
      <h1 class="text-orange-500 dark:text-blue-500 font-medium text-xl px-2">
        Mes dîplomes et formations
      </h1>
    </div>
    <timeline :lines="formations" @callback="callback" />
  </div>
</template>

<script>
import timeline from '~/layouts/timeline.vue'
import cards from '~/layouts/cards.vue'

export default {
  components: { timeline, cards },
  data: () => {
    return {
      formations: [
        {
          name: 'École ENI',
          grade: 'BAC+5 MS2D',
          city: 'Saint-Herblain, France',
          started_at: 'Novembre 2020',
        },
        {
          name: 'École ENI',
          grade: 'Licence Informatique',
          city: 'Saint-Herblain, France',
          obtained_at: 'Octobre 2020',
        },
        {
          name: 'Notre Dame du Roc',
          grade: 'BTS SIO',
          more: 'Option SLAM (développement)',
          city: 'La Roche sur Yon, France',
          obtained_at: 'Juin 2019',
        },
      ],
    }
  },
  methods: {
    callback(index) {
      console.log(index)
    },
  },
}
</script>
