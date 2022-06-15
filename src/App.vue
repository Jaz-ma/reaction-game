<template>
<h1>Reaction Game</h1>
<button @click="startGame" :disabled="isPlaying">Play</button>
<Results/>
<Block v-show="isPlaying" @boxClicked="boxClicked"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  data(){
    return{
      isPlaying:false,
      delay: null

    }
  },
  components: {
    Block,
    Results,   
  },
  methods:{
    startGame(){
      this.delay = 2000 + Math.random()
      setTimeout(()=>{
        this.isPlaying=true
      },)
    },
    boxClicked(){
      this.isPlaying=false
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

