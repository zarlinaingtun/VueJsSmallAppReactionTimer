<template>
    <div class="block" v-if="showBlock">
        Click Here{{delay}}
    </div>
    <h1>Updated</h1>

</template>

<script>
export default {
     props:['delay'],
    data(){
        return {
            showBlock:false
        }
    },
    mounted(){
        setTimeout(()=>{
            this.showBlock=true
        },this.delay);
        console.log("Mounted");
    },
    updated(){
        console.log("Updated");
    },
    unmounted(){
        console.log("Unmounted");
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