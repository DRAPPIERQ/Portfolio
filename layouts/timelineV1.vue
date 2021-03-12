<template>
  <div class="flex">
    <div v-if="linesHeight.length" class="flex-row w-1/12">
      <div class="flex justify-center mt-5">
        <div class="flex-col">
          <div v-for="(lineHeight, index) in linesHeight" :key="index">
            <tlDot v-if="index" />
            <tlLine :class="'h-' + lineHeight" />
          </div>
        </div>
      </div>
    </div>
    <div
      :class="['flex-row', linesHeight.length ? 'w-11/12' : 'w-full', 'pt-6']"
    >
      <slot></slot>
    </div>
  </div>
</template>
<script>
import tlDot from '~/components/timeline/dot.vue'
import tlLine from '~/components/timeline/line.vue'

export default {
  props: {
    linesHeight: {
      type: Array,
      default: () => {
        return []
      },
    },
  },
  components: { tlDot, tlLine },
}
</script>
