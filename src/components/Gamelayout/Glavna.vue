<template>
  <div class="glavna">
      <div id="glavnibroj">
          <p id="ispis">{{ispis}}</p>
      </div><br/>

      <div id="loptica"><p id="pomocnibroj">{{drugiispis[0]}}</p></div>
      <div id="loptica"><p id="pomocnibroj">{{drugiispis[1]}}</p></div>
      <div id="loptica"><p id="pomocnibroj">{{drugiispis[2]}}</p></div>
      <div id="loptica"><p id="pomocnibroj">{{drugiispis[3]}}</p></div>
      <div id="loptica"><p id="pomocnibroj">{{drugiispis[4]}}</p></div>
      <div id="loptica"><p id="pomocnibroj">{{drugiispis[5]}}</p></div>
      <div id="loptica"><p id="pomocnibroj">{{drugiispis[6]}}</p></div>
      <div id="loptica"><p id="pomocnibroj">{{drugiispis[7]}}</p></div>
  </div>
</template>

<script>
export default {
    name: "Glavna",
    data: function(){
        return{
            kombinacija: [],
            ispis: "",
            i: 0,
            drugiispis: [],
            tajmer: 5
        }
    },
    methods:{
        izvlacenje: function(){
            var broj;
            for(let j=0;j<8;j++){
                broj=Math.floor(Math.random()*48)+1;
                if(!this.kombinacija.includes(broj)){
                    this.kombinacija.push(broj);
                }else{
                    --j;
                }
            }
            this.$emit('glkomb',this.kombinacija);
        },

        brojac: function(){
            if(this.tajmer>0 && this.i<this.kombinacija.length+1){
                setTimeout(() => {
                    this.tajmer--;
                    this.brojac();
                }, 1000);
            }else{
                this.ispis=this.kombinacija[this.i];
                this.i++;
                if(this.i!=this.kombinacija.length){
                    this.tajmer=5;
                    this.brojac();
                }
                this.drugiispis.push(this.ispis);
            }
        }
    },
    mounted: function(){
        this.izvlacenje();
        this.brojac();
    }
}
</script>

<style>

</style>