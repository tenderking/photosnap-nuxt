<template>
  <div>
    <the-hero-card :img="imgDark" :isDark="true" :isButton="true">
      <template v-slot:h2> Create and share your photo stories. </template>
      <template v-slot:p
        >Photosnap is a platform for photographers and visual storytellers. We
        make it easy to share photos, tell stories and connect with others.
      </template>
      <template v-slot:btn>Get an invite</template>
    </the-hero-card>
    <the-hero-card
      :img="imgRev"
      :style="{ 'flex-direction': 'row-reverse' }"
      :isButton="true"
    >
      <template v-slot:h2>BEAUTIFUL STORIES EVERY TIME</template>
      <template v-slot:p
        >Photosnap is a platform for photographers and visual storytellers. We
        make it easy to share photos, tell stories and connect with others.
      </template>
      <template v-slot:btn>View the stories</template>
    </the-hero-card>
    <the-hero-card :img="imgLight" :isButton="true">
      <template v-slot:h2> DESIGNED FOR EVERYONE</template>
      <template v-slot:p
        >Photosnap can help you create stories that resonate with your audience.
        Our tool is designed for photographers of all levels, brands, businesses
        you name it.
      </template>
      <template v-slot:btn>View The stories</template>
    </the-hero-card>

    <div class="stories-container">
      <div class="stories-card" v-for="story in slicedStories" :key="story.id">
        <StoryCard :story="story" class="border" />
      </div>
    </div>
    <div class="item-container container">
      <div v-for="feature in slicedFeatures" :key="feature.id">
        <FeatureItem :feature="feature" />
      </div>
    </div>
  </div>
</template>
<script>
import { features } from '../static/features.json'
import { stories } from './../static/stories.json'

export default {
  name: 'IndexPage',
  data() {
    return {
      features,
      stories,
      imgDark: {
        mobile: '/home/mobile/beautiful-stories.jpg',
        tablet: '/home/tablet/beautiful-stories.jpg',
        desktop: '/home/desktop/beautiful-stories.jpg',
      },
      imgRev: {
        mobile: '/home/mobile/create-and-share.jpg',
        tablet: '/home/tablet/create-and-share.jpg',
        desktop: '/home/desktop/create-and-share.jpg',
      },
      imgLight: {
        mobile: '/home/mobile/designed-for-everyone.jpg',
        tablet: '/home/tablet/designed-for-everyone.jpg',
        desktop: '/home/desktop/designed-for-everyone.jpg',
      },
    }
  },
  computed: {
    slicedFeatures() {
      return this.features.slice(0, 3)
    },
    slicedStories() {
      return this.stories.slice(0, 4)
    },
  },
}
</script>
<style lang="scss" scoped>
.item-container {
  padding-block: 1.5rem;
}
@media (min-width: $tablet) {
  .stories-container {
    display: grid;
    grid-template-columns: repeat(2, minmax(350px, 1fr));
  }
}
@media (min-width: $desktop) {
  .item-container {
    display: grid;
    grid-template-columns: repeat(3, minmax(350px, 1fr));
    gap: 1em;
    padding-block: 10rem;
  }
  .stories-container {
    display: grid;
    grid-template-columns: repeat(4, minmax(350px, 1fr));
  }
}
</style>
