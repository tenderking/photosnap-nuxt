<template>
  <button
    :class="[
      isDark ? 'btn--normal--dark' : 'btn--normal--light',
      'btn btn--normal',
    ]"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'NormalButton',
  props: {
    isDark: {
      type: Boolean,
      default: false,
    },
  },
}
</script>
