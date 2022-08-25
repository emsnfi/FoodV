
<template>
  <h2></h2>
  <drop-select :infor="city" @selectItem="filterItem"></drop-select>

  <ul class="travelspot">
    <li v-for="spot in selected" :key="spot.id">
      <img
        class="spotImg"
        :src="spot.Picture1"
        :alt="spot.Name"
        @error="
          $event.target.src =
            'https://memeprod.sgp1.digitaloceanspaces.com/user-wtf/1615961266621.jpg'
        "
      />
      <div class="spotName">
        <a href="">
          <i class="fa-solid fa-heart"> </i>
        </a>
        <span>{{ spot.Name }}</span>
      </div>
      <div class="address">
        <i class="fa-solid fa-map-location-dot"></i>
        <span>{{ spot.Add }}</span>
      </div>
      <div class="openTime">
        <i class="fa-solid fa-clock"></i>
        <span>{{ spot.Opentime }}</span>
      </div>
      <div class="contact">
        <i class="fa-solid fa-phone"></i>
        <a href="tel:+{{spot.Tel}}">+{{ spot.Tel }}</a>
      </div>
    </li>
  </ul>
  <!-- <pageSlide :infor="spots" :offset="12" @set-page="selfupdate"></pageSlide> -->
</template>

<script>
import travelData from "../json/travel.json";
import pageSlide from "./tool/pageSlide.vue";
import dropSelect from "./tool/dropSelect.vue"
export default {
  data() {
    return {
      originData: travelData.slice(0, 100),
      spots: travelData.slice(0, 100),
      city: ["花蓮縣", "臺東縣"],
      selected: travelData.slice(0, 100),
    };
  },
  components: {
    pageSlide,
    dropSelect
  },
  methods: {
    selfupdate(val) {
      this.selected = val;
      // console.log(val)
    },
    filterItem(val) {
      // val 是選擇的 item 名稱
      this.spots = this.originData;
      this.selected = this.spots.filter((searchResult) =>
        searchResult.Region.match(val)
      );
      console.log(this.selected);
      this.spots = this.selected;
    },
  },
  watch: {
    selected: {
      deep: true,
      handler: function () {},
    },
  },
};
</script>

<style scoped>
.travelspot {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.travelspot li {
  border: 1px solid grey;
  border-radius: 10px;
  padding: 15px;
  margin: 5px 0px 5px 5px;
  /* max-width:300px; */
  width: 32%;
  position: relative;
  line-height: 1.8;
}
@media (max-width: 768px) {
  .travelspot li {
    width: 48%;
  }
}
.fa-heart {
  position: absolute;
  font-size: 20px;
  padding: 10px;
}
.spotName {
  position: relative;
}
.spotName .fa-heart {
  position: absolute;
  right: 0px;
  bottom: 0px;
  color: grey;
}
.spotName .fa-heart:hover {
  color: red;
}
.active {
  color: red;
}
.spotImg {
  display: block;
  width: 100%;
  object-fit: cover;
  height: 200px;
  margin-bottom: 10px;
}
svg {
  margin-right: 7px;
}
.contact a {
  color: black;
  text-decoration: none;
}
.contact a:hover {
  /* color:burlywood; */
  color: chocolate;
}
</style>


