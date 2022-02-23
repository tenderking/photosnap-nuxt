<script lang="ts">
import Vue from 'vue'
import { features } from './../static/pricingtable.json'
export default Vue.extend({
  name: 'PricingTable',
  data() {
    return {
      features: features,
      isMobile: null,
    }
  },
  methods: {
    checkScreen() {
      if (process.browser) {
        const screenWidth = window.innerWidth

        this.isMobile = screenWidth < 768
      }
    },
  },
  created() {
    this.checkScreen()
    if (process.browser) window.addEventListener('resize', this.checkScreen)
  },
})
</script>

<template>
  <table v-if="isMobile" class="pricing__mobile font-h4 container">
    <tr class="main-header">
    The feautures
      <!-- <th>Basic</th>
      <th>Pro</th>
      <th>Business</th> -->
    </tr>
    <table v-for="feature in features" :key="feature.id">
      <tr>
        <th class="pricing__feature" colspan="4">{{ feature.feature }}</th>
      </tr>
     

      <tr>
        <td>
       <th class="pricing__plan">Basic</th>

          <span v-if="feature.basic">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="15">
              <path
                fill="none"
                stroke="#000"
                stroke-width="2"
                d="M1 8.124L5.623 13 17 1"
              />
            </svg>
          </span>
          <span class="invisible" v-else> x</span>
        </td>

        <td>
          <th class="pricing__plan">Pro</th>
          <span v-if="feature.pro">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="15">
              <path
                fill="none"
                stroke="#000"
                stroke-width="2"
                d="M1 8.124L5.623 13 17 1"
              /></svg>
          </span>
          <span class="invisible" v-else> x</span>
        </td>

        <td>
          <th class="pricing__plan">Business</th>
          <span v-if="feature.business"
            ><svg xmlns="http://www.w3.org/2000/svg" width="18" height="15">
              <path
                fill="none"
                stroke="#000"
                stroke-width="2"
                d="M1 8.124L5.623 13 17 1"
              /></svg
          ></span>
          <span class="invisible" v-else> x</span>
        </td>
      </tr>
    </table>
  </table>
  <table v-else class="font-h4 pricing__not-mobile">
    <tr>
      <th class="pricing__heads">The feautures</th>
      <th class="pricing__heads">Basic</th>
      <th class="pricing__heads">Pro</th>
      <th class="pricing__heads">Business</th>
    </tr>
    <tr v-for="feature in features" :key="feature.id">
      <td class="pricing__head">{{ feature.feature }}</td>
      <td class="pricing__mark">
        <span v-if="feature.basic"
          ><svg xmlns="http://www.w3.org/2000/svg" width="18" height="15">
            <path
              fill="none"
              stroke="#000"
              stroke-width="2"
              d="M1 8.124L5.623 13 17 1"
            /></svg
        ></span>
      </td>
      <td class="pricing__mark">
        <span v-if="feature.pro"
          ><svg xmlns="http://www.w3.org/2000/svg" width="18" height="15">
            <path
              fill="none"
              stroke="#000"
              stroke-width="2"
              d="M1 8.124L5.623 13 17 1"
            /></svg
        ></span>
      </td>
      <td class="pricing__mark">
        <span v-if="feature.business"
          ><svg xmlns="http://www.w3.org/2000/svg" width="18" height="15">
            <path
              fill="none"
              stroke="#000"
              stroke-width="2"
              d="M1 8.124L5.623 13 17 1"
            /></svg
        ></span>
      </td>
    </tr>
  </table>
</template>
<style lang="scss" scoped>
.pricing__mobile{
  text-align: left;

  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  .pricing__feature{
    padding-block: 2em 0;
  }
  .pricing__plan{
  color: $clr-black;
  opacity: 60%;
  padding-block:0 1em;  
  
}

}

.pricing__not-mobile{
  tr>*{
    padding-block: 2em;
   
  }
}
  .pricing__heads{
    text-align: left;
    padding-right: 4em;
    border-bottom: 1px solid $clr-black;
    
  }
  .pricing__head{
    width: max-content;
       padding-right: 1em;
    
    
    text-align: left;
  }

table {
  border-collapse: collapse;
  padding-block: 1em;
 
}


td {
  border-bottom: 1px solid $clr-grey;
  padding-block: 1em;
  
}
.main-header{
 
  padding-block: 1em;
border-bottom: 1px solid $clr-black;

  
}
.invisible{opacity: 0;}

</style>
