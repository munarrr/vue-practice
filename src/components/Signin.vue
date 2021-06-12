<template>
  <form action="">
   <label >guil</label>
    <label >dd</label>
    <input type="text" name="email" required v-model="password" @change="onchange"/>
    <select v-model="role">
      <option value="designer">Designer</option>
      <option value="developer">Developer</option>
    </select>
<!--    <input id="terms" type="checkbox" required v-model="terms">-->
<!--    <label for="terms">Terms</label>-->
<!--    <input value="Munar" id="a" type="checkbox" required v-model="names">-->
<!--    <label for="a">Munar</label>-->
<!--    <input  value='Mudnar' id="b" type="checkbox" required v-model="names">-->
<!--    <label for="b">popo</label>-->
<!--    <input  value="Muddsdnar" id="c" type="checkbox" required v-model="names">-->
<!--    <label for="c">opo</label>-->

    <input id="check" type="text" v-model="tempsckill" @keypress.enter="Addsckill">
    <div v-for="sckill in sckills" :key="sckill">
      <span @click="deleteSkill(sckill)">{{sckill}}</span>
    </div >
    <div class="submit">
      <button>Create an account</button>
    </div>



    <p>{{email}}</p>
    <p>{{password}}</p>
    <p>{{role}}</p>
    <p>{{terms}}</p>
    <p>Names{{names}}</p>

  </form>
</template>

<script>
export default {
  name: 'Signin',
  data(){
    return{
      email:"",
      password:"",
      role:"",
      terms:false,
      tempsckill:"",
      names:[],
      sckills:[]

    };
  },
  methods:{
    Addsckill(){
    this.sckills.push(this.tempsckill);
    this.tempsckill = "";
    },
    deleteSkill(sckill){
      this.sckills = this.sckills.filter((skill) => skill !== sckill)
    }
  }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
form {
  max-width: 420px;
  margin: 30px auto;
  background-color: #fff;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label {
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.6em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: 700;
}
input,
select {
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: #555;
}
input[type="checkbox"] {
  position: relative;
  top: 2px;
  display: inline-block;
  width: 16px;
  margin: 0 10px 0 0;
}
.pill {
  display: inline-block;
  margin: 20px 10px 0 0;
  padding: 6px 12px;
  background-color: #eee;
  border-radius: 20px;
  font-size: 12px;
  letter-spacing: 1px;
  font-weight: 700;
  color: #777;
  cursor: pointer;
}
button {
  background-color: #0b6dff;
  border: none;
  padding: 10px 20px;
  margin-top: 20px;
  color: #fff;
  border-radius: 20px;
  cursor: pointer;
}
.submit {
  text-align: center;
}
.error {
  color: #ff0062;
  margin-top: 10px;
  font-size: 0.8em;
  font-weight: 700;
}

</style>
