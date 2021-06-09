<template>
  <p>Ваше время реагирование {{score}}</p>
  <p>{{rank}}</p>
</template>

<script>
export default {
  name: 'Result',
  props:["score"],
  data(){
    return {
      rank: null,
    };
    },
    mounted(){
      if (this.score < 250 && this.score >= 0) {
        this.rank = 'Молниеносная Реакция'
      }
      if (this.score < 450 && this.score >= 250) {
        this.rank = 'Шустрые пальцы, качаешься?'
      }
      if (this.score < 650 && this.score >= 450) {
        this.rank = 'Неплохо, но, можно лучше'
      }
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
</style>
