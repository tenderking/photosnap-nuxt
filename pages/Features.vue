<template>
  <div>
    <the-hero-card :img="heroCardFeature" :isDark="true">
      <template v-slot:h2> Features</template>
      <template v-slot:p
        >We make sure all of our features are designed to be loved by every
        aspiring and even professional photograpers who wanted to share their
        stories.
      </template>
    </the-hero-card>
    <div class="item-container container">
      <div v-for="feature in features" :key="feature.id">
        <FeatureItem :feature="feature" />
      </div>
    </div>
    <TheBanner />
  </div>
</template>

<script>
import { features } from '../static/features.json'
import { heroCardFeature } from './../static/heroes.json'
export default {
  data() {
    return {
      features,
      heroCardFeature,
    }
  },
}
</script>

<style lang="scss" scoped>
.item-container {
  padding-block: 1.5rem;
}
@media (min-width: $tablet) {
  .item-container {
    display: grid;
    grid-template-columns: repeat(2, minmax(350px, 1fr));
    gap: 1em;
    padding-block: 2.5rem;
  }
}
@media (min-width: $desktop) {
  .item-container {
    display: grid;
    grid-template-columns: repeat(3, minmax(350px, 1fr));
    gap: 1em;
    padding-block: 10rem;
  }
}
</style>
