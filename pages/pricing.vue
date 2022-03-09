<script>
import TheHeroCard from '~/components/TheHeroCard.vue'
export default {
  components: { TheHeroCard },
  name: 'PricingPage',
  data() {
    return {
      isMonthly: true,
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
      img: {
        mobile: '/pricing/mobile/hero.jpg',
        tablet: '/pricing/tablet/hero.jpg',
        desktop: '/pricing/desktop/hero.jpg',
      },
    }
  },
}
</script>
<template>
  <div class="pricing-container">
    <the-hero-card :img="img" :isDark="true">
      <template v-slot:h2> Pricing</template>
      <template v-slot:p
        >Create a your stories, Photosnap is a platform for photographers and
        visual storytellers. It’s the simple way to create and share your
        photos.
      </template>
    </the-hero-card>
    <div class="pricing">
      <ButtonsToggleButton v-model="isMonthly"/>

      <div class="pricing__cards container">
        <PricingCard :content="basic" :isMonthly="isMonthly" />
        <PricingCard :content="pro" :isMonthly="isMonthly" />
        <PricingCard :content="business" :isMonthly="isMonthly" />
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
  padding-bottom: 8rem;

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
