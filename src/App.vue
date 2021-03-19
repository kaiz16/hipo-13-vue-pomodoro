<template>
  <div id="app">
    <div class="card">
      <div class="cycles">
        <p>Cycles 0</p>
      </div>
      <div class="timer">
        <!-- get a minute & a second from timer -->
        <p>{{ Math.floor(timer / 60) }}:{{ Math.floor(timer % 60) }}</p>
      </div>

      <div class="buttons">
        <button v-on:click="start()">Play</button>
        <button v-on:click="restart()">Restart</button>
      </div>
    </div>
  </div>
</template>

<script>
let counter;
export default {
  name: "App",
  data() {
    return {
      timer: 10,
      isWork: true,
    };
  },
  // watch for timer (watcher)
  watch: {
    timer: function() {
      // stop the timer when it reaches to 0
      if (this.timer < 0){
        // are we in work session? 
        if (this.isWork === true){
          // take a break
          this.isWork = false
        }else{ // we are in break session
          // work again
          this.isWork = true
        }

        this.stop()

        this.restart()

        this.start()
      }
    }
  },
  methods: {
    start() {
      // stop the timer
      this.stop();
      // create the timer
      // setInterval is like an infinite loop that runs every second
      counter = setInterval(() => {
        this.timer = this.timer - 1;
      }, 1000);
    },
    restart() {
      this.timer = 10;
    },
    stop() {
      clearInterval(counter);
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

html,
body {
  height: 100%;
  width: 100%;
  background: #353f4b;
  color: #fff;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  width: 100%;
  /* centering card inside app */
  display: flex;
  align-items: center;
  justify-content: center;
}

.card {
  background: #292f3b;
  width: 20%;
  height: 50%;
  border-radius: 20px;
  padding: 20px;
  /* styling items inside card */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}

.timer {
  font-weight: 600;
  font-size: 2rem;
}
</style>
