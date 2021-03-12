<template>
  <div class="flex justify-center mt-6">
    <div class="flex-col">
      <div
        class="flex flex-row"
        v-for="(line, index) in lines"
        :key="index"
        @click="callback(index)"
      >
        <div
          class="px-2 mt-3 w-40"
          style="min-width: 10rem"
          v-if="line.started_at"
        >
          <p class="text-grey-900 dark:text-grey-100 font-bold text-right">
            {{ line.ended_at ? line.ended_at : 'Depuis' }}
          </p>
          <p class="text-grey-900 dark:text-grey-100 font-bold text-right">
            {{ line.started_at }}
          </p>
        </div>
        <div
          class="px-2 mt-3 w-40"
          style="min-width: 10rem"
          v-else-if="line.obtained_at"
        >
          <p class="text-grey-900 dark:text-grey-100 font-bold text-right">
            Obtenu en
          </p>
          <p class="text-grey-900 dark:text-grey-100 font-bold text-right">
            {{ line.obtained_at }}
          </p>
        </div>
        <div class="px-2 mt-3 w-40" style="min-width: 10rem" v-else></div>
        <div class="mt-6">
          <tlDot />
        </div>
        <div class="-ml-3">
          <tlLine class="min-h-full" />
        </div>
        <div ref="timeline-content" class="pl-3 mt-3">
          <p class="text-orange-500 dark:text-blue-500 font-bold">
            {{ line.name }}
          </p>
          <p class="text-orange-500 dark:text-blue-500 font-medium">
            {{ line.grade }}
          </p>
          <p class="text-grey-900 dark:text-grey-100 italic">
            {{ line.city }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import tlDot from '~/components/timeline/dot.vue'
import tlLine from '~/components/timeline/line.vue'

export default {
  props: {
    lines: {
      type: Array,
      default: () => {
        return []
      },
    },
  },
  components: { tlDot, tlLine },
  methods: {
    callback(index) {
      this.$emit('callback', index)
    },
  },
}
</script>
