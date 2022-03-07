<script>
export default {
  name: 'PricingPage',
  data() {
    return {
      isActive: true,
      pro: {
        title: 'Pro',
        content:
          'More advanced features available. Recommended for photography veterans and professionals.',
        yearlyPrice: '$390.00',
        monthlyPrice: '$39.00',
        type: 'dark',
      },
      business: {
        title: 'Business',
        content:
          'Additional features available such as more detailed metrics. Recommended for business owners.',
        yearlyPrice: '$990.00',
        monthlyPrice: '$99.00',
        type: 'light',
      },
      basic: {
        title: 'Basic',
        content:
          'Includes basic usage of our platform. Recommended for new and aspiring photographers.',
        yearlyPrice: '$190.00',
        monthlyPrice: '$19.00',
        type: 'light',
      },
    }
  },
  methods: {
    togglePricing() {
      console.log('hello')
      this.isActive = !this.isActive
    },
  },
}
</script>
<template>
  <div class="pricing-container">
    <div class="pricing">
      <ButtonsToggleButton
        :isMonthly="isActive"
        @click.native="togglePricing()"
      />
      <div class="pricing__cards container">
        <PricingCard :content="basic" :isMonthly="isActive" />
        <PricingCard :content="pro" :isMonthly="isActive" />
        <PricingCard :content="business" :isMonthly="isActive" />
      </div>
    </div>
    <h1 class="font-h1-h2">Compare</h1>
    <PricingTable />
  </div>
</template>

<style lang="scss" scoped>
.pricing-container {
  display: grid;
  place-items: center;
  .pricing {
    padding-block: 7.5rem;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 2.5rem;

    &__cards {
      display: grid;
      align-items: center;
      gap: 2em;
    }
  }
}
@media (min-width: $desktop) {
  .pricing__cards {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
