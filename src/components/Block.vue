<template>
<div @click="boxClicked" v-if="showBlock">
    click me
</div>
</template>

<script>
export default {
    props:['delay'],
    data(){
        return{
            showBlock: false,
        }
    },
    methods:{
        boxClicked(){
            this.$emit('boxClicked')
        }
    },
    mounted(){
        console.log('mounted')
        setTimeout(() => {
            this.showBlock= true
        }, this.delay);
    },
    updated(){
         console.log('updated')   
    },
    unmounted(){
        console.log('unmounted')
    }
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

