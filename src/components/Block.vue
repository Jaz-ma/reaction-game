<template>
<div @click="boxClicked">
    click me
</div>
</template>

<script>
export default {
    methods:{
        boxClicked(){
            this.$emit('boxClicked')
        }
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

