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
  /*
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
  created() {
    this.checkScreen()
    if (process.browser) window.addEventListener('resize', this.checkScreen)
  },
  */
}
</script>
<template>
  <div class="hero" :class="{ dark: isDark }">
    <picture>
      <source media="(min-width: 1200px)" :srcset="img.desktop" />
      <source media="(min-width: 768px)" :srcset="img.tablet" />
      <img :src="img.mobile" class="hero__img" />
    </picture>
    <!-- <img :src="getImg" alt="hero-img" class="hero__img" /> -->
    <div class="hero__text" :class="{ dark: isDark }">
      <h2 class="font-h1-h2 hero__text-title">
        <slot name="h2"></slot>
      </h2>
      <p class="font-normal hero__text-content">
        <slot name="p"></slot>
      </p>
      <ButtonsFlatButton v-show="isButton" :isDark="true">
        <slot name="btn"></slot>
      </ButtonsFlatButton>
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
  &__text {
    display: grid;
    width: 100%;
    place-content: center;
    padding-inline: 1.75rem;
    padding-block: 4.5rem;
    &-title,
    &-content {
      padding-bottom: 1rem;
    }
    &-content {
      max-width: 35ch;
      opacity: 50%;
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
      margin: 0;
      padding: 0;
      padding-inline: 3.75rem;
    }
    .dark {
      position: relative;
      background-color: $clr-black;
      color: $clr-white;
      &::before {
        content: '';
        height: 30%;
        width: 6px;
        left: 0;
        top: 8rem;

        position: absolute;
        background: linear-gradient(#ffc593 0%, #bc7198 51.95%, #5a77ff 100%);
      }
    }
  }
}
@media (min-width: $desktop) {
  .hero {
    &__text {
      padding-inline: 7rem;
    }
  }
}
</style>
