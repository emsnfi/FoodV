
<template>


  <h2></h2>
  <ul class="travelspot">
    <li v-for="spot in spots" :key="spot.id" class="col-4">
      <img class="spotImg" :src="spot.Picture1" alt={{spot.Picture1}}>
      <div class="spotName">
        
        <a href=""><i class="fa fa-heart-o"></i></a>
        <span>{{spot.Name}}</span>
      
      
      </div>
      <div class="address">{{spot.Add}}</div>
      <div class="openTime">{{spot.Opentime}}</div>
      <div class="contact"><a href="tel:+{{spot.Tel}}">+{{spot.Tel}}</a></div>
      

    </li>
  </ul>

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

<style scoped>

.travelspot{
  display:flex;
  flex-wrap:wrap;
  justify-content: space-between;
}

.travelspot li{
  padding:20px 0px;
  margin:5px ;
  max-width:250px;
  position:relative;
}

.fa-heart{
  position:absolute;
  font-size: 20px;
}

.spotName{
  display: flex;

}
.spotName i{
  margin-right:10px;
}
.spotImg{
  display:block;
  width:250px;
  height:150px;
}
</style>


