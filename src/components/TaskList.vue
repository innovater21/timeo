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
    //   tasks:[],
    //   task: {
    //     id:1,
    //     name:'Dummy task',
    //     duration:'3.5hrs',
    //     startTimeStamp: '22/08/1997',
    //     endTimeStamp: '22/08/1997'
    //   }
    }
  },
  methods:{
    populateTasks(task) {
        this.tasks.push(task);
    }
  },
  mounted() {
    // let tempData = {
    //     id:1,
    //     name:'Dummy task 1',
    //     duration:'1.5hrs',
    //     startTimeStamp: '22/08/1997',
    //     endTimeStamp: '22/08/1997'
    //   };
    // let tempData2 = {
    //     id:2,
    //     name:'Dummy task 2',
    //     duration:'2.5hrs',
    //     startTimeStamp: '22/08/1997',
    //     endTimeStamp: '22/08/1997'
    //   };
    // this.populateTasks(tempData);
    // this.populateTasks(tempData2);
  }
}
</script>

<style>
    .list__wrapper {
        max-height: 500px;
        overflow: auto;
        /* box-shadow: 
    12px 12px 16px 0 rgba(0, 0, 0, 0.25),
    -8px -8px 12px 0 rgba(255, 255, 255, 0.3); */
    }
</style>
