<script>
export default {
  name: 'TheHeroCard',
  props: {
    img: {
      type: Object,
    },
    isButton: {
      type: Boolean,
      default: false,
    },
    isDark: {
      type: Boolean,
      default: false,
    },
    isButton: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      getImg: null,
    }
  },

  methods: {
    checkScreen() {
      if (process.browser) {
        const mediaMobile = window.matchMedia('(max-width: 768px)')
        const mediaTablet = window.matchMedia('(min-width: 768px)')
        const mediaDesktop = window.matchMedia('(min-width: 1200px)')

        if (mediaMobile.matches) {
          this.getImg = this.img.mobile
        }
        if (mediaTablet.matches) {
          this.getImg = this.img.tablet
        }
        if (mediaDesktop.matches) {
          this.getImg = this.img.desktop
        }
      }
    },
  },
  mounted() {
    this.checkScreen()
    if (process.browser) window.addEventListener('resize', this.checkScreen)
  },
}
</script>
<template>
  <div class="hero" :class="{ dark: isDark }">
    <!-- <picture>
      <source media="(min-width: 1200px)" :srcset="img.desktop" />
      <source media="(min-width: 768px)" :srcset="img.tablet" />
      <img :src="img.mobile" class="hero__img" />
    </picture> -->
    <!-- <template> -->
      <div>
        <img :src="getImg" alt="hero-img" class="hero__img" />
      </div>
    <!-- </template> -->
    <div class="hero__text" :class="{ dark: isDark }">
      <div class="hero__styling-div container">
        <h2 class="font-h1-h2 hero__text-title">
          <slot name="h2"></slot>
        </h2>
        <p class="font-normal hero__text-content">
          <slot name="p"></slot>
        </p>
        <ButtonsFlatButton v-show="isButton" :isDarkBtn="isDark">
          <slot name="btn"></slot>
        </ButtonsFlatButton>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.hero {
  width: 100%;

  .dark {
    position: relative;
    background-color: $clr-black;
    color: $clr-white;
    .hero__styling-div {
      position: relative;
      &::before {
        content: '';
        width: 8rem;
        height: 6px;
        top: 0;
        position: absolute;
        left: 1.75rem;

        margin-bottom: 1em;

        background: linear-gradient(#ffc593 0%, #bc7198 51.95%, #5a77ff 100%);
      }
    }
  }
  &__text {
    // display: grid;
    // place-content: center;
    display: flex;

    justify-content: center;
    align-items: center;

    width: 100%;
    .hero__styling-div {
      padding-block: 4.5rem;
      flex-grow: 0;
    }

    &-title,
    &-content {
      padding-bottom: 1rem;
    }

    &-title {
      max-width: 14ch;
    }

    &-content {
      max-width: 35ch;
      opacity: 0.5;
    }
  }
  &__img {
    min-width: 100%;
  }
}

@media (min-width: $tablet) {
  .hero {
    display: flex;
    &__text {
      padding-block: auto;
      .hero__styling-div {
        padding-block: 0;
        flex-grow: 1;
      }
    }

    .dark {
      position: relative;
      background-color: $clr-black;
      color: $clr-white;
      .hero__styling-div {
        position: relative;
        &::before {
          content: '';
          height: 100%;
          width: 6px;
          left: 0;

          position: absolute;
          background: linear-gradient(#ffc593 0%, #bc7198 51.95%, #5a77ff 100%);
        }
      }
    }
  }
}
@media (min-width: $desktop) {
  .hero {
    &__text {
      width: 45%;

      flex-grow: 1;
    }
    &__img {
      width: 55%;
    }
  }
}
</style>
