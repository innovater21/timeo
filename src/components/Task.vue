<template>
  <div class="task__wrapper neumorphic">
    <img class="profile__image" src="https://picsum.photos/id/237/30/30" width="30" height="30">
    <p style="margin:0">{{ task.name }}<br>Project 1</p>
    <p style="margin:0">{{ task.duration }}</p>  
  </div>
</template>

<script>
import Task from './Task.vue';

export default {
  name: 'Task',
  components: {
    Task,
  },
  props:["task"],
  data () {
    return {
      
    }
  },
  methods:{
   
  },
  mounted() {
    
  }
}
</script>

<style>
    .task__wrapper {
        margin: 20px;
        height: 30px;
        display: grid;
        grid-template-columns: 60px 1fr 1fr;
        padding: 20px;
    }
    .profile__image {
      border-radius: 50%;
    }
</style>
