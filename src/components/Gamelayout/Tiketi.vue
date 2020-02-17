<template>
    <div id="Tiketi">
        <button  id="generisi" v-on:click="generisi">Generiši tiket</button>
    </div>
</template>

<script>
export default {
  name: 'Tiketi',
  data: function(){
      return{
          komb: [],
          tiket: 1,
      }
  },
  methods:{
      generisi: function(){
          var br;
          for(let i=0;i<6;i++){
              br=(Math.floor(Math.random()*48)+1);
              if(!this.komb.includes(br)){
                this.komb.push(br);
                                  }else{
                --i;}
          }
        this.komb.sort(function(a, b){return a - b});
        var newKomb={
            idtiketa: this.tiket,
            kombinacija: this.komb,
            broj: 0,
        }
        if(this.komb.length == 6){
                    this.printMe(newKomb);
                    this.komb=[];
                    this.tiket++;
                    this.$emit('add-komb', newKomb);
                }},
        printMe(obj) {
            const WinPrint = window.open('', '', 'left=0,top=0,width=345,height=545,toolbar=0,scrollbars=0,status=0');

            WinPrint.document.write(`
                <!DOCTYPE html>
                <html lang="en">
                <head>
                    <meta charset="UTF-8">
                    <meta name="viewport" content="width=device-width, initial-scale=1.0">
                    <meta http-equiv="X-UA-Compatible" content="ie=edge">
                    <title>Document</title>
                    <style>
                        .container {text-align: center; height: 300px; width: 300px; border: 1px solid black;}
                        .container ul {list-style: none;}
                        #tiket {font-size: 24px; font-style: italic;}
                        span {font-weight: bold;}
                        .brojevi p {
                            width: 20px;
                            margin: 5px auto;
                            font-size: 16px;
                            border: 1px solid black;
                            border-radius: 10px;
                        }
                    </style>
                </head>
                <body>
                    <div class="container">
                        <p id="tiket">Tiket: <span>#${obj.idtiketa}</span></p>
                        <hr>
                        <div class="brojevi">
                            <p>${obj.kombinacija[0]}</p>
                            <p>${obj.kombinacija[1]}</p>
                            <p>${obj.kombinacija[2]}</p>
                            <p>${obj.kombinacija[3]}</p>
                            <p>${obj.kombinacija[4]}</p>
                            <p>${obj.kombinacija[5]}</p>
                        </div>
                        <hr>
                        <p>Gagy Lucky</p>
                    </div>
                </body>
                </html>
            `);

            WinPrint.document.close();
            WinPrint.focus();
        }
      }
}
</script>

<style scoped>
#generisi{
  margin-top:5%;
  background-color: white; 
  color: black; 
  border: 4px solid  #3D173E;
  border-radius: 3vh;
  padding: 30px 60px;
  text-align: center;
  display: inline-block;
  font-size: 25px;
  transition-duration: 0.4s;
  cursor: pointer;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  font-weight: bold;
}

#generisi:hover {
  background-color:  #3D173E;
  color: white;
}
</style>