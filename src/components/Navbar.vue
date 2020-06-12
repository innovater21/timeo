<template>
  <div class="navbar">
      <img src="./../assets/images/logo.png" height="60px" style="object-fit:contain;justify-self:flex-start">
  </div>
</template>

<script>
import Navbar from './Navbar.vue';

export default {
  name: 'Navbar',
  components: {
    
  },
  data () {
    return {
      
    }
  },
  methods:{
    // populateTasks(task) {
    //     this.tasks.push(task);
    // }
  },
  mounted() {
    
  }
}
</script>

<style>
    .navbar {
        display: flex
    }
</style>
