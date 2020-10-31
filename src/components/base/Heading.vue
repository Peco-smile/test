<template>
  <component
    :is="tag"
    class="v-heading mb-3 font-weight-light font"
    :class="[$vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2']"
  >
    <slot />
  </component>
</template>

<script>
  export default {
    name: 'BaseHeading',

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
  .v-heading{
    letter-spacing: 3px !important;
  }
  .font {
    font-family: 'Noto Sans JP', sans-serif !important;
  }
</style>
