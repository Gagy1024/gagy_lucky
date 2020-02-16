<template>
<div id="game">
    <Brojcanik />
</div>
</template>

<script>
import Brojcanik from './../components/Brojcanik.vue';
export default {
  name: 'Game',
  components:{
    Brojcanik,
  }
  }
</script>

<style scoped>
#game{
    align:center;
}
</style>