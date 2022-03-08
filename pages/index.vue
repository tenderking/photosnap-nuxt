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
  </div>
</template>
<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  data() {
    return {
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
})
</script>
