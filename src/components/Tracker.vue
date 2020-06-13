<template>
    <div class="tracker neumorphic">
        <input style="height:40px;border:1px solid #ccc;border-radius:15px;padding:10px" type="text" v-model="taskName" placeholder="Enter task description" />
        <div class="counter">{{ hour }} : {{ minutes }} : {{ seconds }}</div>
        <button class="button_class play" @click="startTimer"><img src="https://img.icons8.com/flat_round/64/000000/play--v1.png"/></button>
        <button class="button_class stop" @click="stopTimer"><img src="https://img.icons8.com/flat_round/64/000000/stop.png"/></button>
    </div>
</template>

<script>

export default {
  name: 'Tracker',
  components: {
  },
  data () {
    return {
      timer: null,
      totalTime: 0,
      taskName:null
    //   totalTime: ( * 60),
    }
  },
  computed: {
    hour: function() {
        const hour = Math.floor(this.totalTime / 3600);
        return this.padTime(hour);
    },
    minutes: function() {
        const minutes = Math.floor(this.totalTime / 60) - this.hour*60;
        return this.padTime(minutes);
    },
    seconds: function() {
        const seconds = this.totalTime - (this.minutes * 60) - (this.hour * 3600);
        return this.padTime(seconds);
    }
  },
  methods:{
    startTimer() {
       this.timer = setInterval(() => this.countdown(), 1000);
    },
    stopTimer() {
        clearInterval(this.timer);
        this.$emit('stop-time', {duration:this.totalTime, name: this.taskName });
        this.timer = null;
    },
    padTime: function(time) {
        return (time < 10 ? '0' : '') + time;
    },
    countdown: function() {
        this.totalTime++;
    }
  },
  mounted() {
    
  }
}
</script>

<style>
    .projects__wrapper {
        max-width: 250px;
    }
    .tracker {
      display: grid;
      grid-template-columns: 1fr 1fr 80px 80px;
      height: 100px;
      padding: 10px;
      align-items: center;
    }
    .button_class {
      border-radius: 50%;
      border: none;
      background: transparent;
    }
    .counter {
      font-weight: bolder;
      line-height: 40px;
      font-size: 35px;
      display: flex;
      align-items: center;
      padding: 20px;
    }
</style>
