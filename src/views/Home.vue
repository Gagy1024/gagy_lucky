<template>
  <div class="home">
    
    <Header />
    <button id="pokreni">Pokreni igru</button>
    

    <vue-particles color="#dedede" :particleOpacity="0.7"
        :particlesNumber="80"
        shapeType="circle"
        :particleSize="4"
        linesColor="#dedede"
        :linesWidth="1"
        :lineLinked="true"
        :lineOpacity="0.4"
        :linesDistance="150"
        :moveSpeed="3"
        :hoverEffect="true"
        hoverMode="grab"
        :clickEffect="true"
        clickMode="push"></vue-particles>
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
body {
	font-family: Impact;
  background-image: url('../assets/background.jpg');
  background-size: 100%;
}

</style>