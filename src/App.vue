<template>
  <div id="app">
<h1>Проверь свою рекцию</h1>
  <button @click="startGame" :disabled="isPlayng">Начать игру</button>
  <div v-if="delay">
    <Block :delay="delay"   @reactionTime="test"/>
  </div>
    <Result v-if="showResults" :score="score"/>
  </div>
</template>

<script>
import Block  from "./components/Block.vue";
import Result from "./components/Result.vue";

export default {
  name: 'App',
  components: {
    Result,
    Block
  },
  data(){
    return{
      isPlayng:false,
      showResults: false,
      delay:null,
      score:null,
    };
  },
  methods: {
    startGame() {
      this.delay = Math.floor(Math.random() * 5000);
    },
    test(reactionTime) {
     this.score= reactionTime;
     this.showResults = true
    }
  }
  }
</script>

<style>
  #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
  button[disabled]{
    opacity:0.3;
    cursor: not-allowed
  ;

  }
</style>
