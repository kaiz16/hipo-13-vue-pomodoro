<template>
  <div id="app">
    <div class="card">
        <div class="cycles">
          <p>Cycles 0</p>
        </div>
        <div class="timer">
          <p>00:00</p>
        </div>

        <div class="buttons">
          <button>Play</button>
          <button>Restart</button>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App"
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

.card{
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

.timer{
  font-weight: 600;
  font-size: 2rem;
}
</style>
