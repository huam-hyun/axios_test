<template>
  <div id="app">
    <div>
      <h3>axios 테스트</h3>
      <p>get요청</p>
      <button @click="get">get요청</button>
      <br>
      <p>이름으로 get요청</p>
      <input type="text" placeholder="name" v-model="name">
      <button @click="get2">get요청2</button>
      <br><hr>
      <p>name: {{name}}</p>
      <p>age: {{age}}</p>
    </div>

  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  components: {
    
  },
  data(){
    return {
      name: '',
      age: '',
    }
  },
  methods:{
    get(){
      axios.get('/get1').then(res =>{
        this.name = res.name;
        this.age = res.age;
      })
    },
    get2(){
      axios.get('/get2', {params:{name: this.name}}).then(res =>{
        this.name = res.name;
        this.age = res.age;
      })
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
</style>
