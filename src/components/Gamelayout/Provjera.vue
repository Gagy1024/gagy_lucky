<template>
  <div class="provjera">
      <Header />
      <div id="kombinacija">
          <p id="manje">Glavna kombinacija</p>
          <p id="vece"><b>{{ispkomb[0]}},{{ispkomb[1]}},{{ispkomb[2]}},{{ispkomb[3]}},{{ispkomb[4]}},{{ispkomb[5]}},{{ispkomb[6]}},{{ispkomb[7]}}</b></p>
      </div>
      <div class="listici" v-bind:key="tiket" v-for="tiket in korisnik">
          <p id="manje">Broj tiketa: {{tiket.idtiketa}}</p>
          <p id="vece">Kombinacija: 
              {{tiket.kombinacija[0]}},
              {{tiket.kombinacija[1]}},
              {{tiket.kombinacija[2]}},
              {{tiket.kombinacija[3]}},
              {{tiket.kombinacija[4]}},
              {{tiket.kombinacija[5]}}</p>
          <p id="manje">Broj pogodaka: {{tiket.broj}}</p>
      </div>
  </div>
</template>

<script>
import Header from './../Header';

export default {
    name: "Provjera",
    components:{
        Header
    },
    props:['niz','glavna'],
    data: function(){
        return{
            korisnik: this.niz,
            komb: this.glavna,
            ispkomb: ""
        }
    },
    methods:{
        rezultat: function(){
            this.ispkomb=this.komb[0];
            this.ispkomb.sort(function(a, b){return a - b});
            for(let i=0;i<this.korisnik.length;i++){
                for(let j=0;j<this.korisnik[i].kombinacija.length;j++){
                    if(this.ispkomb.includes(this.korisnik[i].kombinacija[j])){
                        this.korisnik[i].broj++;
                    }
                }
            }
        }
    },
    created:function(){
        this.rezultat();
    }
}
</script>

<style scoped>
#kombinacija{
    background-color: #3D173E;
    border-radius: 8px;
    width: 350px;
    height: 90px;
    align-content: center;
    margin-left: 40%;
}
#manje{
    color: white;
    padding: 5px;
    font-weight: bold;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
#vece{
    color: white;
    font-size: 22px;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
.listici{
    background-color: #2E116E;
    border-radius: 8px;
    width: 350px;
    height: 122px;
    align-content: center;
    margin-left: 40%;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}
</style>