
<template>
<div v-if="showBlock">
  <div class="block" @click="stopTimer">Нажми на меня</div>
</div>

  <p>{{result}}</p>
</template>

<script>
export default {
  name: 'Block',
  props:["delay"],
  data(){
    return{
      showBlock:false,
      timer:null,
      reactionTime:0,

    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTime();
    }, this.delay);
  },
  methods:{
    startTime(){
    this.timer = setInterval(() => {
      this.reactionTime += 10;
    },10);
  },
  stopTimer(){
    clearInterval(this.timer);
    this.$emit('reactionTime',this.reactionTime)
  },
},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.block {
  width: 400px;
  border-radius: 20px;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
