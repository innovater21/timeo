<template>
  <div class="task__wrapper neumorphic">
      {{ task }}
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
    // populateTasks(task) {
    //     this.tasks.push(task);
    // }
  },
  mounted() {
    
  }
}
</script>

<style>
    .task__wrapper {
        margin: 20px;
        height: 200px;
    }
</style>
