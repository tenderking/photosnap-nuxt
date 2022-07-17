<script>
// we want to toggle the svg circle position when clicked and swap colors
//
export default {
  data() {
    return {
      isActive: this.value,
      circlePos: 16,
    }
  },

  props: {
    value: { type: Boolean },
  },

  methods: {
    toggleButton() {
      this.$emit('input', !this.isActive)
    },
  },
  watch: {
    value(newValue, oldValue) {
      newValue === true ? (this.circlePos = 16) : (this.circlePos = 48),
        (this.isActive = this.value)
    },
  },
}
</script>

<template>
  <div class="main">
    <h3 class="font-h3" :class="{ active: !isActive }" @click="toggleButton()">
      Monthly
    </h3>
    <svg
      @click="toggleButton()"
      width="64"
      height="32"
      viewBox="0 0 64 32"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <rect
        width="64"
        height="32"
        rx="16"
        fill="#DFDFDF"
        :class="{ rect: isActive }"
      />
      <circle
        :class="{ active: isActive }"
        :cx="circlePos"
        cy="16"
        r="12"
        fill="black"
      />
    </svg>
    <h3 class="font-h3" :class="{ active: isActive }" @click="toggleButton()">
      Yearly
    </h3>
  </div>
</template>

<style lang="scss" scoped>
.main {
  display: flex;
  gap: 2rem;
  .active {
    color: $clr-grey;
    fill: $clr-white;
    -webkit-transition: all 0.2s ease-in-out;
    -moz-transition: all 0.2s ease-in-out;
    transition: all 0.2s ease-in-out;
  }
  .rect {
    fill: $clr-black;
  }
  circle,
  rect {
    -webkit-transition: all 0.2s ease-in-out;
    -moz-transition: all 0.2s ease-in-out;
    transition: all 0.2s ease-in-out;
  }
}
</style>
