
<template>
  <p v-for="spot in spots" :key="spot.Id">
    {{spot.Name}}
  </p>
</template>

<script>

import travelData from '../json/travel.json'

export default {
  data() {
    return {
      spots: travelData,
    };
  },

   mounted(){

  }
};
</script>