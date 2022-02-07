<template>
  <div class="card">
    <!-- <img class="card__img" :src="story.imgUrlDesktop" :alt="story.title" /> -->
    <nuxt-img
      class="card__img--mobile"
      :src="story.imgUrlMobile"
      :alt="story.title"
    />
    <nuxt-img
      class="card__img--desktop"
      :src="story.imgUrlDesktop"
      :alt="story.title"
    />
    <div class="card__text-container">
      <p class="font-body">{{ story.createdAt }}</p>
      <h3 class="font-h3">{{ story.title }}</h3>
      <p class="font-body">{{ story.createdBy }}</p>
      <h4 class="font-h4 card__text-container--h4">
        Read Story
        <svg xmlns="http://www.w3.org/2000/svg" width="43" height="14">
          <g fill="none" fill-rule="evenodd" stroke="#000">
            <path class="arrow" d="M0 7h41.864M35.428 1l6 6-6 6" />
          </g>
        </svg>
      </h4>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StoryCard',
  props: { story: Object },
}
</script>

<style lang="scss" scoped>
.card {
  position: relative;

  width: 100%;

  &__img--mobile {
    width: 100%;
  }
  &__img--desktop {
    display: none;
  }
  &__text-container {
    outline: #5a77ff dot;
    position: absolute;
    z-index: 999;
    margin: 0 auto;
    inset: auto auto 0 0;

    font-family: Arial, sans-serif;
    color: #fff;
    padding: 2.5rem;

    &__text-container > * + * {
      padding-block: 0.25rem;
    }
    &--h4 {
      border-top: solid 0.0125rem $clr-grey;
      display: flex;
      justify-content: space-between;
      line-height: 1rem;
      padding-top: 1.125rem;
      margin-top: 1.125rem;
      .arrow {
        stroke: $clr-white;
      }
    }
  }

  &:hover {
    transform: translateY(-2rem);
    transition: transform ease-in-out 0.2s;
    &:after {
      /* Rectangle */
      content: '';

      height: 10px;
      width: 100%;
      position: absolute;
      display: inline-block;
      margin-bottom: 1em;

      background: linear-gradient(
          26.57deg,
          #ffc593 0%,
          #bc7198 43.29%,
          #5a77ff 83.33%
        )
        red;
      z-index: 9999;
    }
  }
}
@media (min-width: $tablet) {
  .card {
    position: relative;

    min-width: minmax(260px, 100%);

    &__img--mobile {
      display: none;
    }
    &__img--desktop {
      display: block;
      width: 100%;
    }
  }
}
</style>
