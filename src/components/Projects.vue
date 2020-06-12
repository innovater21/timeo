<template>
  <div class="projects__wrapper neumorphic">
      <div v-for="project in projects" :key="project.id">
          {{ project.name }}
      </div>
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
      projects: [
          {
              id:1,
              name: 'Project 1'
          },
          {
              id:2,
              name: 'Project 2'
          },
          {
              id:3,
              name: 'Project 3'
          },
          {
              id:4,
              name: 'Project 4'
          },
          {
              id:5,
              name: 'Project 5'
          },
          {
              id:6,
              name: 'Project 6'
          },
          {
              id:7,
              name: 'Project 7'
          },
      ]
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
    .projects__wrapper {
        max-width: 250px;
    }
</style>
