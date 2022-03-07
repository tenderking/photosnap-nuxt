<template>
  <div>
    <the-hero-card :img="img" :isDark="true">
      <template v-slot:h2> Features</template>
      <template v-slot:p
        >We make sure all of our features are designed to be loved by every
        aspiring and even professional photograpers who wanted to share their
        stories.
      </template>
    </the-hero-card>
    <p>features page</p>
    <TheBanner />
  </div>
</template>

<script>
export default {
  data() {
    return {
      img: {
        mobile: '/features/mobile/hero.jpg',
        tablet: '/features/tablet/hero.jpg',
        desktop: '/features/desktop/hero.jpg',
      },
    }
  },
}
</script>
