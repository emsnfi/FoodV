<template>
    
    <ul class="spotSave" >
        <li v-for="" :key=""></li>
    </ul>

</template>

<script>

export default{

data(){
    return{

    }
},

props:{
    infor:{
        type:Array,

    }
},
methods(){
    function addItem(event){
         event.preventDefault();
    }
}


}

</script>