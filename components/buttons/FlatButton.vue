<template>
  <button class="btn flat-button" :class="[isDarkBtn ? 'light-btn' : 'dark-btn']">
    <span
      class="flat-button__content font-h4"
    >
      <slot>{{ message }}</slot>
    </span>
    <svg xmlns="http://www.w3.org/2000/svg" width="43" height="14">
      <g fill="none" fill-rule="evenodd">
        <path
          d="M0 7h41.864M35.428 1l6 6-6 6"
          id="target"
        />
      </g>
    </svg>
  </button>
</template>

<script>
export default {
  name: 'FlatButton',
  props: {
    message: {
      // It can be either one or several types for one attribute
      type: String,
      default: '',
    },
    isDarkBtn: {
      type: Boolean,
      default: false
    },
  },
}
</script>

<style lang="scss" scoped>
.dark-btn {
  stroke: $clr-black;
  color: $clr-black;
}

.light-btn {
  stroke: $clr-white;
  color: $clr-white;
}

.flat-button {
  display: flex;
  gap: 22px;

  &:hover {
      text-decoration: underline;
    }
}
</style>
