<template>
  <div class="featured">
    <img
      src="@/static/stories/desktop/moon-of-appalacia.jpg"
      alt=""
      class="featured__img--desktop"
    />
    <img
      src="@/static/stories/tablet/moon-of-appalacia.jpg"
      alt=""
      class="featured__img--tablet"
    />
    <img
      src="@/static/stories/mobile/moon-of-appalacia.jpg"
      alt=""
      class="featured__img--mobile"
    />
    <div class="featured__text container">
      <h4 class="font-h4">Last Months's Featured Story</h4>
      <h1 class="font-h1-h2 featured__text--title">
        Hazy full moon of appalachia
      </h1>
      <div class="featured__info">
        <p class="font-body featured__info--date">March 2nd 2020</p>
        <p class="font-body">by John Appleseed</p>
      </div>
      <p class="font-body featured__text--description">
        The dissected plateau area, while not actually made up of geological
        mountains, is popularly called "mountains," especially in eastern
        Kentucky and West Virginia, and while the ridges are not high, the
        terrain is extremely rugged.
      </p>
      <ButtonsFlatButton class="flat-button_light-text">
        Read The STory
      </ButtonsFlatButton>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.featured {
  &__img--mobile {
    width: 100%;
  }
  &__img--tablet,
  &__img--desktop {
    display: none;
  }
  &__info {
    display: flex;
    gap: 1rem;
    &--date {
      opacity: 75%;
    }
  }

  &__text {
    background: $clr-black;
    color: $clr-white;
    padding-block: 7.325rem;

    &--title {
      max-width: 10ch;
      color: $clr-white;
    }
    &--description {
      max-width: 35ch;
      color: $clr-white;
      opacity: 60%;
    }

    z-index: 9;
    & > * + * {
      padding-block: 0.75rem;
    }
  }
}
@media (min-width: $tablet) {
  .featured {
    position: relative;

    &:after {
      /* Rectangle */
      content: '';
      inset: 0 0 0 0;

      position: absolute;
      display: inline-block;

      background: radial-gradient(
        68.48% 68.48% at 0% 100%,
        #ffc593 0%,
        rgba(188, 113, 152, 0.496968) 52.36%,
        rgba(90, 119, 255, 0.0001) 100%
      );
      mix-blend-mode: normal;
      opacity: 0;
      transition: opacity 0.3s;
    }
    &:hover:after {
      opacity: 0.49;
      transition: opacity 1s;
    }
    &__img--tablet {
      display: block;
      width: 100%;
      background: white;
    }
    &__text {
      position: absolute;
      inset: 0 auto auto 0;

      background: 0;
    }
    &__img--mobile,
    &__img--desktop {
      display: none;
    }
  }
}

@media (min-width: $desktop) {
  .featured {
    &__img--desktop {
      display: block;
      width: 100%;
    }
    &__img--mobile,
    &__img--tablet {
      display: none;
    }
  }
}
</style>
