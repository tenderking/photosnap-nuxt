<script>
export default {
  data() {
    return {
      isActive: false,
      circlePos: 16,
    }
  },

  methods: {
    toggleButton() {
      // console.log('hi')
      this.isActive = !this.isActive
    },
  },
  watch: {
    isActive(newValue, oldValue) {
      newValue === true ? (this.circlePos = 48) : (this.circlePos = 16)
    },
  },
}
</script>

<template>
  <div class="main">
    <h3 class="font-h3" :class="{ active: isActive }">Monthly</h3>
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
    <h3 class="font-h3" :class="{ active: !isActive }">Yearly</h3>
  </div>
</template>

<style lang="scss" scoped>
.main {
  display: flex;
  gap: 2rem;
  .active {
    color: $clr-grey;
    fill: $clr-white;
  }
  .rect {
    fill: $clr-black;
  }
}
</style>
