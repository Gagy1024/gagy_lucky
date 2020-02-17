<template>
  <div id="game">
    <div v-if="svicer">
      <div v-if="svicer2">
        <Provjera v-on:load="Provjera" v-bind:niz="korisnickekombinacije" v-bind:glavna="glkomb"/>
      </div>
      <div v-else>
        <Glavna v-on:glkomb="unos"/>
      </div>
    </div>
    <div v-else>
      <div id="brojcanik">
      <Brojcanik v-on:load="Brojcanik" />
      </div>
      <div id="dodati">
      <Tiketi v-on:add-komb="dodaj" />
      </div>
    </div>
  </div>
</template>

<script>
import Brojcanik from './../components/Brojcanik.vue';
import Tiketi from './../components/Gamelayout/Tiketi.vue';
import Glavna from './../components/Gamelayout/Glavna.vue';
import Provjera from './../components/Gamelayout/Provjera.vue';
export default {
  name: 'Game',
  components:{
    Brojcanik,
    Tiketi,
    Glavna,
    Provjera
  },
  data: function(){
    return{
      korisnickekombinacije: [],
      glkomb:[],
      svicer: false,
      svicer2: false,
    }
  },
  created: function(){
    var self=this;
    setTimeout(()=>{
                self.svicer=!self.svicer;
                },60000);
    setTimeout(()=>{
                self.svicer2=!self.svicer2;
                },105000);
  },
  methods:{
    dodaj: function(newKomb){
      this.korisnickekombinacije.push(newKomb);
    },
    unos: function(glkomb){
      this.glkomb.push(glkomb);
    }
  }
}
</script>

<style scoped>
#game{
    align:center;
}
</style>