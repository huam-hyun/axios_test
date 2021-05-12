<template>
  <div id="app">
    <div>
      <h3>axios 테스트</h3>
      <p>get요청</p>
      <button @click="get">get요청</button>
      
      <br><hr>
      <p>brand_name: {{name}}</p>
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
      axios.get('myapp/brand/').then(res =>{
        this.name = res[0].brand_name;
      })
    },
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
