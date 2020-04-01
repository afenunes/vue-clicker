<template>
  <div>
    <div class="score">Score: {{ score }}</div>
    <div class="clickbutton">
      <button class="center" v-on:click="plus">Click Here</button>
      <div class="step">Step: {{step}}</div>
    </div>

    <h1>{{ counter }}</h1>

    <div>
      <button class="center" v-on:click="upgrade1">Upgrade 1</button>
    </div>
    <div>
      <button class="center" v-on:click="upgrade2">Upgrade 2</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Game',
  components: {
  },
  data() {
    return {
      counter: 0,
      score: 0,
      step: 1,
    };
  },
  methods: {
    plus() {
      this.counter += this.step;
      this.score = this.score < this.counter ? this.counter : this.score;
    },
    reset() {
      this.counter = 0;
    },
    upgrade1() {
      if (this.counter >= 10) {
        this.counter -= 10;
        this.step += 1;
      }
    },
    upgrade2() {
      if (this.counter > 100) {
        this.counter -= 100;
        this.step += 10;
      }
    },
  },
};
</script>

<style scoped>
.center {
  height: 60%;
  padding: 10px;
  border: none;
}

.score {
    position: fixed;
    top: 0;
    right: 0;
    padding: 15px;
}

.clickbutton{
  display: flex;
  flex-direction: row;
  justify-content: center;
  padding-left: 7%;
}

.step {
  padding: 10px;
}
</style>
