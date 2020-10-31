<template>
  <component
    :is="tag"
    class="display-1 v-heading mb-3 font-weight-light font"
  >
    <slot />
  </component>
</template>

<script>
  export default {
    name: 'BaseSubheading',

    props: {
      tag: {
        type: String,
        default: 'h1',
      },
    },
  }
</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP&display=swap');
  .font {
    font-family: 'Noto Sans JP', sans-serif !important;
  }
</style>
