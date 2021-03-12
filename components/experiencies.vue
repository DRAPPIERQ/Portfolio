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
    <timeline :lines="experiencies" />
  </div>
</template>

<script>
import timeline from '~/layouts/timeline.vue'
import cards from '~/layouts/cards.vue'

export default {
  components: { timeline, cards },
  data: () => {
    return {
      experiencies: [
        {
          name: 'Agence Cube',
          grade: 'Contrat Apprentissage',
          city: 'La Roche sur Yon, France',
          started_at: 'Novembre 2020',
        },
        {
          name: 'Agence Cube',
          grade: 'Contrat Professionalisation',
          city: 'La Roche sur Yon, France',
          started_at: 'Juillet 2019',
          ended_at: 'Octobre 2020',
        },
        {
          name: 'Agence Cube',
          grade: 'Stage',
          city: 'La Roche sur Yon, France',
          started_at: 'Janvier 2019',
          ended_at: 'Février 2019',
        },
        {
          name: 'Hygiène Expert',
          grade: 'Stage',
          city: 'Les Herbiers, France',
          started_at: 'Mai 2018',
          ended_at: 'Juin 2018',
        },
        {
          name: 'LetMeRepair',
          grade: 'Itérim',
          city: 'La Roche sur Yon, France',
          started_at: 'Juillet 2017',
          ended_at: 'Août 2017',
        },
        {
          name: 'Dworkin',
          grade: 'Stage',
          city: 'République tchèque, Prague',
          started_at: 'Novembre 2016',
          ended_at: 'Décembre 2016',
        },
      ],
    }
  },
}
</script>
