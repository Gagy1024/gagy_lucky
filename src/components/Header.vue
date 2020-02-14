<template>
  <div class="header">
      <img id="logo" src="./../assets/logo-spider.png"/>
      <div id="dugmici">
      <router-link to="/"><button id="prvi">Početna stranica</button></router-link>
      <router-link to="/about"><button id="drugi">Info stranica</button></router-link>
      </div>
    </div>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style scoped>
 .header {
        height: 10vh; width: 100%;
        margin: 0;
        box-sizing: border-box;
        background-color: rgba(169, 169, 169, 0.4);
        display: fixed;
        align-content: center;
    }

    #prvi {
        margin-left: 0%;
        margin-top: -50%;
        padding: 2vh;
        border: none; border-radius: 3vh;
        background-color: #7E0404;
        font-weight: bold;
        font-size: 3vh;
        height: 100%;
    }

    #prvi:hover {
        background: #58034F;
    }

    #drugi {
        margin-left: 10%;
        margin-top: -50%;
        padding: 2vh;
        border: none; border-radius: 3vh;
        background-color: #7E0404;
        font-weight: bold;
        font-size: 3vh;
        height: 100%;
    }

    #drugi:hover {
        background: #58034F;
    }

    #logo{
        height: 100%;
        margin-left: -50%;
        margin-top: 0%;
        display: absolute;
    }
    
    #dugmici{
        margin-left:10%;
        margin-top:-3%;
        display: absolute;
    }
</style>