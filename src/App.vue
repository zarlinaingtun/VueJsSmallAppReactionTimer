<template>
      <h1>How Fast Can You Catch Me ?</h1>
      <button class="play" @click="start" :disabled="isPlaying">Play</button>
      <div v-if="isPlaying">
        <Block :delay="delay"/>
      </div>
</template>

<script>
import Block from "./components/Block.vue";
export default {
  data(){
    return{
      isPlaying:false,
      delay:null
    }
  },
  components: {
    Block
  },
  methods:{
    start(){
      this.isPlaying=true,
      this.delay=Math.floor(2000+Math.random()*5000);
    }
  }
}
</script>

<style scoped>
.play{
  width:100px;
  height: 50px;
 
  background-color: rgb(145, 163, 197);
  color:#fff;
  border-radius: 10px;
  border:0;
  font-size: 16px;
}
.play:focus{
  transform: scale(0.89);
  background-color: rgb(45, 233, 45);
}
</style>
