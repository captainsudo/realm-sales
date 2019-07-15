<template>
  <div id="app">
    <div class="question">{{steps[slide].text}}</div>
    <div class="buttons">
      <button @click="nextTrue()" v-if="steps[slide].trueButton">{{steps[slide].trueButton}}</button>
      <button @click="nextFalse()" v-if="steps[slide].falseButton">{{steps[slide].falseButton}}</button>
    </div>
  </div>
</template>

<script>
import Steps from "./components/slides";
export default {
  name: "app",
  components: {},
  data() {
    return {
      slide: 0,
      steps: Steps
    };
  },
  methods: {
    nextTrue() {
      this.slide = this.steps[this.slide].trueNext;
    },
    nextFalse() {
      this.slide = this.steps[this.slide].falseNext;
    }
  },
  mounted() {}
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
