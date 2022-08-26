<script>
export default {
  name: 'FeatureItem',
  props: { feature: Object },
}
</script>
<template>
  <div class="item">
    <nuxt-img :src="feature.imgUrl" class="item__img" />
    <h3 class="font-h item__title">{{ feature.feature }}</h3>
    <p class="font-body item__content">{{ feature.description }}</p>
  </div>
</template>

<style lang="scss" scoped>
.item {
  display: grid;
  place-items: center;
  justify-content: center;
  grid-template-rows: 5rem auto 1fr;
  padding-block: 1em;
  &__title {
    padding: 0 0 1rem 0;
    margin: 0;
  }
  &__img {
    max-width: 100%;
    padding: 0 0 2rem 0;
  }
  &__content {
    max-width: 35ch;
    text-align: center;
    opacity: 0.5;
  }
}
</style>
