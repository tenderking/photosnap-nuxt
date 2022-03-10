<template>
  <div class="card-container">
    <div class="card" :class="{ dark: content.type === 'dark' }">
      <h3 class="font-h3">
        {{ content.title }}
      </h3>
      <p class="font-body">{{ content.content }}</p>
      <h2 class="font-h2">
        {{ isMonthly ? content.monthlyPrice : content.yearlyPrice }}
      </h2>
      <p class="font-body">{{ isMonthly ? 'per month' : 'per year' }}</p>
      <ButtonsNormalButton>Pick Plan</ButtonsNormalButton>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isMonthly: {
      type: Boolean,
      default: true,
    },
    content: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style lang="scss" scoped>
.card-container {
  position: relative;
  .card {
    text-align: center;

    padding: 56px 24px 40px;
    background: $clr-light-grey;
    h3 {
      padding-bottom: 1rem;
    }
    p {
      padding-bottom: 2.125rem;
      color: $clr-black;
      opacity: 0.6;
    }
    h2 {
      padding-bottom: 0.5rem;
    }
  }
  .dark {
    background: $clr-black;
    color: $clr-white;
    padding: 88px 24px 70px;
    p {
      padding-bottom: 2.125rem;
      color: $clr-white;
      opacity: 0.6;
    }
    &::before {
      content: '';
      width: 100%;
      height: 6px;
      top: 0;
      position: absolute;
      left: 0;

      margin-bottom: 1em;

      background: linear-gradient(#ffc593 0%, #bc7198 51.95%, #5a77ff 100%);
    }
  }
}
</style>
