<template>
<h1>Reaction Game</h1>
<button @click="startGame" :disabled="isPlaying">Play</button>
<Results v-if="finished" :reactionTime="reactionTime"/>
<Block v-if="isPlaying" :delay="delay" @boxClicked="boxClicked"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  data(){
    return{
      isPlaying:false,
      finished:false,
      delay: null,
      reactionTime:null,


    }
  },
  components: {
    Block,
    Results,   
  },
  methods:{
    startGame(){
      this.delay = 2000 + Math.random()
      this.isPlaying= true
      this.finished=false
    },
    boxClicked(reactionTime){
      this.isPlaying=false
      this.finished=true
      this.reactionTime=reactionTime
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
}
</style>

