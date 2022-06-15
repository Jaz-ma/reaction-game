<template>
    <p>
        Your Reaction time is {{this.reactionTime}} ms
    </p>
    <p>
        {{this.rank}}
    </p>
</template>

<script>
export default {
    props:['reactionTime'],
    data(){
        return{
            rank:null,
        }
    },
    mounted(){
        if(this.reactionTime < 250){
            this.rank = 'wow is u sanic?'
        }else if (this.reactionTime <450){
            this.rank='nothing special'
        }else{
            this.rank='my grandma would do better'
        }
    }
}
</script>