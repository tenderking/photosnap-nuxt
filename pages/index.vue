<template>
  <div>
    <p>Hello world</p>
    <nuxt-link to="/features"> Go to features </nuxt-link>
    <nuxt-link to="/stories"> Go to stories </nuxt-link>
  </div>
</template>
<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
})
</script>
