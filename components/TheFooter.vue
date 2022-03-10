<template>
  <footer>
    <div class="footer container">
      <TheLogo class="light footer__logo" />
      <SocialIcons class="footer__socials" />
      <nav class="footer__nav">
        <ul class="footer__nav-ul" role="list">
          <li><nuxt-link to="/" class="font-link">Home</nuxt-link></li>
          <li>
            <nuxt-link to="/stories" class="font-link">Stories</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/features" class="font-link">Features</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/pricing" class="font-link">Pricing</nuxt-link>
          </li>
        </ul>
      </nav>

      <ButtonsFlatButton :isDarkBtn="true" class="footer__btn-cta"
        >Get an invite</ButtonsFlatButton
      >

      <p class="font-body footer__copyright">
        Copyright 2019. All Rights Reserved
      </p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'TheFooter',
}
</script>

<style lang="scss">
.footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;

  padding-block: 3.5rem;
  background-color: $clr-black;
  &__nav {
    padding-block: 1rem 3rem;
    text-align: center;
    ul {
      line-height: 2em;
    }
  }
}

@media (min-width: $tablet) {
  .footer {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr 1fr;
    gap: 0;
    padding-block: 4rem;
    &__logo {
      grid-column: 1 / span 1;
      grid-row: 1 / span 1;
    }
    &__socials {
      grid-column: 1 / span 1;
      grid-row: 4 / span 1;
    }
    &__nav {
      padding-block: 1em;
      grid-column: 1 / span 1;
      grid-row: 2 / span 1;
      ul {
        line-height: 1em;
        display: flex;
        gap: 1em;
      }
    }
    &__btn-cta {
      grid-column: -1;
      grid-row: 1 / span 1;
      justify-self: flex-end;
    }
    &__copyright {
      grid-column: -1 / span 1;
      grid-row: 4 / span1;
      justify-self: flex-end;
      color: $clr-white;
    }
  }
}

@media (min-width: $desktop) {
  .footer {
    grid-template-columns: 1fr 1fr 1fr;
    &__nav {
      grid-column: 2 / span 1;
      grid-row: 1 / span 4;
      ul {
        text-align: left;
        flex-direction: column;
      }
    }
  }
}
</style>
