<template>
  <div class="brojcanik">
      <div id="bubanj">
          <p id="broj">{{pocetak}}</p>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            pocetak: 60
        }
    },
    methods:{
        odbrojavanje: function(){
            if(this.pocetak>0){
                setTimeout(()=>{
                this.pocetak-=1;
                this.odbrojavanje();
                },1000)
            }
        }
    },
    mounted: function(){
        this.odbrojavanje();
    }
}
</script>

<style scoped>
#bubanj{
        width: 300px;
        height: 300px;
        border-radius: 300px;
        background-color: #3D173E;
        text-align: center;
        font-size: 150px;
        margin-left: 42%;
        margin-top: 15%;
}

#broj{
    padding: 60px;
    color: white;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    text-align: center;
}
</style>