<template>
<h1>Reaction Game</h1>
<button @click="startGame">Play</button>
<Results/>
<Block v-show="showBlock" @boxClicked="boxClicked"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  data(){
    return{
      showBlock:false,

    }
  },
  components: {
    Block,
    Results,   
  },
  methods:{
    startGame(){
      setTimeout(()=>{
        this.showBlock=true
      },Math.random()*2000)
    },
    boxClicked(){
      this.showBlock=false
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
h1{
  color: rgb(16, 88, 28);
}
button{
  padding: 1rem 2rem;
  border-radius: 10px;
  color: white;
  font-size: 23px;
  background: rgb(12, 100, 49);
}
</style>

