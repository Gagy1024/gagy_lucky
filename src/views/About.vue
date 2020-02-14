<template>
  <div class="about">
    <Header />
    <div class="tekst">
      <p>
        <br/>
        <b>GAGY LUCKY</b><br/>
        <br/>
        Projekat GAGY LUCKY je internet aplikacija, koja je radjena u Frontend metodi.<br/>
        Te koja se igra po osnovnim principima svih bingo igara na sreću.<br/>
        <br/>
        <img id="author" src="./../assets/author.jpg"/>
        <br/>
        Devloped by: <br/>
        <b>Dragan Todorović</b><br/>
      </p>
    </div>
    <img id="slika" src="./../assets/logo-spider.png"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from './../components/Header.vue'

export default {
  name: 'home',
  components: {
    Header
  }
}
</script>

<style>
.tekst{
   margin-top:2%;
   background-color: rgba(169, 169, 169, 0.4);
   border-radius: 25px;
   width: 90vh;
   margin-left:25%;
}

.tekst p{
  color: white;
}

#slika{
  display: fixed;
  width:15%;
  margin-top:0%;
}
</style>