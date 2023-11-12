<template>
    <div class="registroCliente">
        <h3>Registrarse</h3> <h4>(en pruebas)</h4>
        <div class="components">
       <RegistroClientes/>
       <DesginFooter class="designfooter"/>
        </div>
    </div>
</template>

<script>
import  RegistroClientes from "@/components/RegistroClientes.vue";
import "bootstrap";
import "bootstrap/dist/css/bootstrap.min.css";
import DesginFooter from '@/components/DesignFooter.vue';

export default {
name: 'RegistroUserView',

  components: {
    RegistroClientes,
    DesginFooter
    
  }
}
</script>


<style>

.designfooter{
  margin-top: 20%;
}

</style>