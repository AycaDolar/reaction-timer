<template>
  <div class="divButton" v-if="showTheDiv" @click="stopTimer">Click Here</div>
</template>

<script>


export default {
  props: ["delay"],
  data() {
    return {
      showTheDiv: false,
      timer: null,
      stopped: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showTheDiv = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer: function () {
        this.timer = setInterval(() => {
            this.stopped += 10
        }, 10) 
    },
    stopTimer: function () {
        clearInterval(this.timer)
        console.log(this.stopped)
        this.$emit('end',this.stopped)
    },
  },
};
</script>

<style>
.divButton {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 30em;
  display: grid;
  height: 18em;
  margin-top: -9em;
  margin-left: -15em;
  border: 1px solid #ccc;
  background-color: pink;
}
</style>
