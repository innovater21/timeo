<template>
  <div class="list__wrapper">
    <Task v-for="task in tasks" :key="task.id" :task="task">
    </Task>
  </div>
</template>

<script>
import Task from './Task.vue';

export default {
  name: 'Tasks',
  components: {
    Task,
  },
  props: ['tasks'],
  data () {
    return {
    
    }
  },
  methods:{
    populateTasks(task) {
        this.tasks.push(task);
    }
  },
  mounted() {
    
  }
}
</script>

<style>
    .list__wrapper {
        margin-top: 30px;
        max-height: 450px;
        overflow: auto;
    }
</style>
