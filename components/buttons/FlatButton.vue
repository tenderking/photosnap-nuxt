<template>
  <button class="btn flat-button">
    <span
      class="flat-button__content font-h4"
      :class="isDark ? 'flat-button_light-text' : 'flat-button_dark-text'"
    >
      <slot>{{ message }}</slot>
    </span>
    <svg xmlns="http://www.w3.org/2000/svg" width="43" height="14">
      <g fill="none" fill-rule="evenodd" stroke="#000">
        <path
          d="M0 7h41.864M35.428 1l6 6-6 6"
          :id="isDark ? 'target' : 'target-light'"
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
    isDark: {
      type: Boolean,
    },
  },
}
</script>

<style lang="scss">
.flat-button {
  display: flex;
  gap: 22px;
  &_dark-text {
    color: $clr-black;
    #target {
      stroke: $clr-black;
    }
  }
  &_light-text {
    color: $clr-white;
    #target-light {
      stroke: $clr-white;
    }
  }
}
</style>
