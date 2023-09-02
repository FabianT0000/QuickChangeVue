<template>

<div class="loginUser">
        <h3>Login</h3><h4>(en pruebas)</h4>
        <div class="components">
        <FormLogin/>
        
        <DesginFooter class="designfooter"/>
        </div>
    </div>
</template>

<script>
import  FormLogin from "@/components/FormLogin.vue";
import DesginFooter from '@/components/DesignFooter.vue';



export default {
  name: 'LoginView',
  components: {
    FormLogin,
    DesginFooter
  }
}
</script>

<style>

.designfooter{
  margin-top: 20%;
}

</style>