<template>
  <div
    v-html="require(`~/assets/${icon}${outline ? '-outline' : ''}.svg?raw`)"
  />
</template>

<script>
export default {
  props: {
    icon: { type: String, default: 'default' },
    outline: { type: Boolean, default: false },
  },
}
</script>
