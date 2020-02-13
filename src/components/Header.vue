<template>
  <div class="header">
      <img src="./../assets/logo-spider.png"/>
      <router-link to="/"><button>Početna stranica</button></router-link>
      <router-link to="/about"><button>Info stranica</button></router-link>
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
        display: grid;
        grid-template-columns: 10vw 10vw 10vw 20vw 20vw;
        justify-content: space-evenly;
        align-content: center;
    }
    .header button {
        margin-left: 120%;
        padding: 1vh;
        border: none; border-radius: 1vh;
        background-color: #7E0404;
        font-weight: bold;
        font-size: 3vh
    }

    .header button:hover {
        background: #58034F;
    }
    .header img {
        height: 9vh;
        margin-left: 100%;
    }

    @media (orientation: landscape) {
        .header {
            grid-template-columns: 10vw 15vw 15vw 5vw 5vw;
        }
    }
</style>