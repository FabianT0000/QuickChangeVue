<template>
  <div class="home">
    <img class="img-home" alt="Vue logo" src="../assets/banner.jpg">
    <div class="texto-home">
      <h1>EXPLORA LO DESCONOCIDO</h1>
    </div>
    <HelloWorld class="helloworld"/>
 

    <DesginFooter class="designfooter"/>
    
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import "bootstrap";
import "bootstrap/dist/css/bootstrap.min.css";
import DesginFooter from '@/components/DesignFooter.vue';


export default {
  name: 'HomeView',
  components: {
    HelloWorld,
    DesginFooter
  }
}

</script>

<style>

.img-home{
  width: 100%;
  height: 70vh;
  background-image: linear-gradient(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75)),
    url(../assets/banner.jpg);
  background-size: cover;
  background-position: center;
}
.home h1{
    position: absolute;
    top: 30%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.designfooter{
  margin-top: 20%;
}


</style>