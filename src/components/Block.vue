<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        Click Here{{delay}}
    </div>
    <h1>Updated</h1>

</template>

<script>
export default {
     props:['delay'],
    data(){
        return {
            showBlock:false,
            timer:null,
            score:0
        }
    },
    mounted(){
        setTimeout(()=>{
            this.showBlock=true;
            this.startTimer();
        },this.delay);
        console.log("Mounted");
    },
    updated(){
        console.log("Updated");
    },
    unmounted(){
        console.log("Unmounted");
    },
    methods:{
        startTimer(){
            this.timer=setInterval(()=>{
                this.score+=50;
                console.log(this.score);
            },50);
        },
        stopTimer(){
            clearInterval(this.timer);
            console.log("Stop Score is="+this.score);
        }
    }
   
}
</script>

<style scoped>
    .block{
        width:200px;
        height: 200px;

        background-color: red;
        color:#fff;

        margin:100px auto;
    }
</style>