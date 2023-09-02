<template>
    <div class="registroCliente">
        <h3>Registrarse</h3> <h4>(en pruebas)</h4>
        <div class="components">
       <RegistroClientes/>
        </div>
    </div>
</template>

<script>
import  RegistroClientes from "@/components/RegistroClientes.vue";
import "bootstrap";
import "bootstrap/dist/css/bootstrap.min.css";

export default {
name: 'RegistroUserView',

  components: {
    RegistroClientes,
    
  }
}
</script>