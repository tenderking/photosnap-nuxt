<template>
  <div class="banner container">
    <h2 class="font-h1-h2">
      We're in Beta.<br />
      Get your invite<br />
      today!
    </h2>

    <ButtonsFlatButton
      class="flat-button_light-text"
      message="Get an invite"
    ></ButtonsFlatButton>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.banner {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  gap: 1em;
  background: url('@/static/shared/mobile/bg-beta.jpg');
  background-size: cover;
  color: white;
  padding-block: 4.25rem;
  position: relative;
  &:after {
    /* Rectangle */
    content: '';

    width: 128px;
    height: 6px;
    left: 94px;
    top: 0;
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

@media (min-width: $tablet) {
  .banner {
    background: url('@/static/shared/tablet/bg-beta.jpg');
    background-size: cover;
    &:after {
      /* Rectangle */
      content: '';

      width: 6px;
      height: 100%;
      left: 0;
      top: 0;
      position: absolute;
      display: inline-block;
      margin-bottom: 1em;
    }
  }
}
@media (min-width: $desktop) {
  .banner {
    background: url('@/static/shared/desktop/bg-beta.jpg');
    background-size: cover;
  }
}
</style>
