<template>
<div @click="stopTimer" v-if="showBlock">
    click me
</div>
</template>

<script>
export default {
    props:['delay'],
    data(){
        return{
            showBlock: false,
            timer: null,
            reactionTime:0,
        }
    },
    methods:{
        boxClicked(){
            this.$emit('boxClicked',this.reactionTime)
        },
        startTimer(){
            this.time= setInterval(()=>{
                this.reactionTime+=10
            },10)
        },
        stopTimer(){
            clearInterval(this.timer)
            console.log(this.reactionTime)
            this.boxClicked()
        }
    },
    mounted(){
        console.log('mounted')
        setTimeout(() => {
            this.showBlock= true
            this.startTimer()
        }, this.delay);
    },
    
}
</script>

<style scoped>
div{
    padding: 11rem 10px;
    color: white;
    font-size: 23px;
    background: green;
    width: 32%;
    float: center;
    margin: auto;
    margin-top: 2rem;
    border-radius: 31px;
}
</style>

