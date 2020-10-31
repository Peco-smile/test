<template>
  <p
    class="title font-weight-light font"
    style="line-height: 1.7 !important;"
  >
    <slot />
  </p>
</template>

<script>
  export default {
    name: 'BaseText',
  }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP&display=swap');

.font {
    font-family: 'Noto Sans JP', sans-serif !important;
  }
</style>