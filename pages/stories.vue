<template>
  <div>
    <div class="stories-container">
      <div class="stories-card" v-for="story in storiesList" :key="story.id">
        <StoryCard :story="story" class="border" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { stories } from './../static/stories.json'
export default Vue.extend({
  data() {
    return {
      storiesList: stories,
    }
  },
})
</script>
<style lang="scss" scoped>
.stories-container {
  display: flex;
  flex-wrap: wrap;
  flex-flow: 1;
  width: 100vw;
  margin-inline: auto;
  .stories-card {
    flex-grow: 1;
  }
}
</style>
