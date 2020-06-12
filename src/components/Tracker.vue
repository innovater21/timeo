<template>
    <div class="tracker neumorphic">
        <input type="text" v-model="taskName" />
        <div>{{ hour }} : {{ minutes }} : {{ seconds }}</div>
        <button @click="startTimer">Start Timer</button>
        <button @click="stopTimer">Stop Timer</button>
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
</style>
