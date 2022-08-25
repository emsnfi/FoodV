<template>


<div class="search" >
  <input v-model="keyWord" type="text" class="searchbox">

  <a href ="#"><i class="fa fa-search" @click.prevent="filterSearch" v-on:keyup.enter="filterSearch"></i></a>


</div>

</template>


<script>


export default{
    data() {
        return {
            keyWord: "",
            result: []
        };
    },
    props: {
        infor: {
            type: Array,
            required: true
        },
    },
    computed: {
    //   filterSearch() {
    //     this.$emit('filter',this.);
    //     return this.infor.filter(searchResult => searchResult.name.match(this.keyWord));
    //   }
    },
    methods: {
        filterSearch() {
         
            this.result = this.infor.filter(searchResult => searchResult.name.match(this.keyWord));
            this.$emit("filter", this.result);
            console.log(this.keyWord, "fdsf");
            // return this.infor.filter(searchResult => searchResult.name.match(this.keyWord));
            

            
        }
    },

}

</script>


<style scoped>
.search{
  display:flex;
  align-items: center;
  position:relative;
}

.search a{
  font-size: 20px;
  
  right:8px;
   position: absolute;
   padding:10px;
   color:black;
}
.searchbox{
  width:240px;
  height:40px;
  border-radius: 10px;
 padding:12px;

}

</style>

