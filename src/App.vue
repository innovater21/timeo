<template>
  <div id="app">
    <Navbar></Navbar>
    <div class="main__wrapper">
      <Projects></Projects>
      <div style="padding:0 20px">
        <Tracker @stop-time="addNewTask"></Tracker>
        <TaskList :tasks="tasks"></TaskList>
      </div>
    </div>
  </div>
</template>

<script>
import TaskList from './components/TaskList.vue';
import Navbar from "./components/Navbar.vue";
import Projects from "./components/Projects";
import Tracker from "./components/Tracker";
export default {
  name: 'app',
  // components: {
    // Navbar,
  //   Tracker,
  //   TaskList,
  //   Projects,
  // },
  components: {
    TaskList,
    Navbar,
    Projects,
    Tracker
  },
  data () {
    return {
      // msg: 'Welcome to Your Vue.js App'
      tasks:[],
      taskId:3,
      task: {
        id:null,
        name:null,
        duration:null,
        startTimeStamp: null,
        endTimeStamp: null
      }
    }
  },
  methods: {
    populateTasks(task) {
      this.tasks.push(task);
    },
    addNewTask(taskObject) {
      console.log(taskObject);
      let newTask = {};
      newTask.id = this.taskId;
      newTask.name = taskObject.name;
      newTask.duration = taskObject.duration;
      console.log(newTask);
      console.log(this.tasks);
      this.populateTasks(newTask);
      this.taskId++;
    }
  },
  mounted() {
    let tempData = {
        id:1,
        name:'Dummy task 1',
        duration:'1.5hrs',
      };
    let tempData2 = {
        id:2,
        name:'Dummy task 2',
        duration:'2.5hrs',
      };
    this.populateTasks(tempData);
    this.populateTasks(tempData2);
  }
}
</script>

<style>
html {
  background-color: #f2f3f7;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
  padding: 0 15%;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
.main__wrapper {
  display: grid;
  grid-template-columns: 220px 4fr;
}
.neumorphic {
  background: #f2f3f7;
  border-radius: 15px;
  box-shadow: -2px -2px 4px 0px #ffffff, 3px 4px 10px 0px rgba(0, 0, 0, .25);
}
*::-webkit-scrollbar {
  width: 5px;
}
*::-webkit-scrollbar-track {
  background: #CFD8DC;
}
*::-webkit-scrollbar-thumb {
  background-color: #90A4AE ;
  border-radius: 6px;
  border: 3px solid var(#90A4AE);
}
</style>
