<template>
  <div>
    <div class="container">
      <!-- <form id="cliente-form" @submit.prevent="iniciarSesion"> -->
      <form id="cliente-form">
        <div class="mb-3">
          <label for="userInput" class="form-label" name="usuario">Usuario:</label>
          <input type="text" id="userInput" class="form-control" placeholder="Ingresa tu usuario" required v-model="username"/>
        </div>

        <div class="mb-3">
          <label for="exampleInputPassword1" class="">Password</label>
          <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Ingresa tu contraseña" required v-model="contrasena"/>
        </div>
        <div class="mb-3 form-check">
          <input type="checkbox" class="form-check-input" id="exampleCheck1" />
          <label class="form-check-label" for="exampleCheck1">Check me out</label>
        </div>
        <div class="button-box">
          <button type="submit" class="btn btn-primary" id="IniciarSesion" name="iniciarSesion" @click="login">
            Iniciar sesion
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      username: "",
      contrasena: "",
    };
  },
  methods: {
    login() {
        axios
        .post("http://localhost:8080/api/usuarios/login", {
          username: this.username,
          contrasena: this.contrasena,
        })

        .then((response) => {
          console.log("Bienvenido:" );
          
          alert(response.data);
          location.reload();
          this.$router.go(0);
          this.nomusuariouser = "";
          this.passwuser = "";
        })
        .catch((error) => {
          console.log("error");
          console.error("Error al iniciar sesion:", error);
        });
    },
  },
};
</script>
<style>
.container {
  background-color: rgb(212, 214, 230);
  padding: 4%;
  width: 60%;
  border-radius: 15px;
}

label {
  display: flex;
}
</style>
