<script>
import headercon from './components/Header.vue'


export default {
  
  data() {
    return {
      count: 0,
      currentPath: window.location.hash
    }
  },
  components: {
    headercon,

  },
  methods: { 
    increment() {
      this.count++
      console.log('click')
    }
  },
  mounted() {
    this.increment()
    console.log('mounted')

    
  }
}
</script>


<template>

<headercon></headercon>



  
</template>





<style scoped>

/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
