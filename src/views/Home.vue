<template>
  <div class="home">
    
    
    <div id="dugme">
      <Header />
    <router-link id="router" to="/Game"><button id="pokreni">Pokreni igru</button></router-link>
    </div>

    <div id="pozadina">
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
  width:98%;
  height:100%;
}

#dugme{
  position: absolute;
  width: 99%;
  height: 99%;
}

#pokreni{
  margin-top:18%;
  background-color: white; 
  color: black; 
  border: 4px solid #7E0404;
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

#pokreni:hover {
  background-color: #7E0404;
  color: white;
}

#pozadina{
  margin-top: 0%;
}

#glavnibroj{
  font-size: 140px;
	text-decoration-color: black;
  font-style: bold;
	display: inline-block;
	align-content: center;
	background-image: url('../assets/glavnaloptica.png');
	animation: grow 5s ease infinite;
  width: 300px; height: 300px;
}

#ispis{
    margin-top: 23%;
}

#loptica{
  height: 150px;
  width: 150px;
  background-image: url('../assets/pomocna.png');
  border-radius: 50%;
  display: inline-block;
  margin-right: 5px;
  text-align: center;
  font-size: 50px;
  font-style: bold;
  align-content: center;
  vertical-align: bottom;
  animation: grow 1.3s infinite ease-in-out alternate;
}

#pomocnibroj{
    align:center;
}

@keyframes grow {
  from {
    transform: scale(0);
  }
  to {
    transform: scale(1);
  }
}
</style>