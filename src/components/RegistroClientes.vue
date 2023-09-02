<template>
  <div class="container">
    <form id="cliente-form" @submit.prevent="guardar">
      <div class="mb-3">
        <label for="idInput" class="form-label" >(No Colocar codigo para guardar)codigo:</label >
        <input type="text" id="idInput" class="form-control" name="id_usuario" placeholder="Ingresa tu nombre" required  v-model="id_usuario"  />
      </div>
      <div class="mb-3">
        <label for="nombres" class="form-label" >Nombres:</label>
        <input type="text" id="nombres" name="nombres" class="form-control" placeholder="Ingresa tu nombre" required v-model="nombres" />
      </div>
      <div class="mb-3">
        <label for="lastNameInput" class="form-label" name="apellidosuser">
          Apellidos:
        </label>
        <input type="text" id="lastNameInput" class="form-control" placeholder="Ingresa tus apellidos" required v-model="apellidos" />
      </div>
      <label for="type-id">Tipo de documento:
        <select name="tipodocumuser" id="type-id" class="form-select-sm" value="tipo_documento" required v-model="tipo_documento" >
          <option value="" selected>Elige una opcion:</option>
          <option value="cedula">Cedula</option>
          <option value="pasaporte">Pasaporte</option>
          <option value="nit">NIT</option>
          <option value="cedula extranjera">Cedúla de extranjeria</option>
        </select> </label><br />
      <div class="mb-3">
        <label for="nDocInput" class="form-label" name="ndocumuser">N°Documento:
        </label>
        <input type="text" id="nDocInput" class="form-control" placeholder="Ingresa tu numero de documento" required v-model="nDocumento"/>
      </div>
      <div class="mb-3">
        <label for="telInput" class="form-label" name="teluser">
          Telefono:
        </label>
        <input type="text" id="telInput" class="form-control" placeholder="Ingresa tu telefono" required v-model="telefono"/>
      </div>
      <div class="mb-3">
        <label for="paisInput" class="form-label" name="pais_user">
          Pais:
        </label>
        <input type="text" id="paisInput" class="form-control" placeholder="Ingresa tu pais" required v-model="pais"/>
      </div>
      <div class="mb-3">
        <label for="ciudadInput" class="form-label" name="ciudad_user">Ciudad:</label>
        <input type="text" id="ciudadInput" class="form-control" placeholder="Ingresa tu ciudad" required v-model="ciudad"/>
      </div>
      <div class="mb-3">
        <label for="inputEmail" class="form-label" name="correo_user">Email:
        </label>
        <input type="email" class="form-control" id="inputEmail" aria-describedby="emailHelp"
          placeholder="Ingresa tu email" required v-model="correo"/>
      </div>
      <div class="mb-3">
        <label for="userInput" class="form-label" name="nomusuariouser">Usuario:
        </label>
        <input type="text" id="userInput" class="form-control" placeholder="Ingresa tu usuario" required v-model="username" />
      </div>

      <div class="mb-3">
        <label for="inputPassword" class="" name="passwuser" >Password</label>
        <input type="password" class="form-control" id="inputPassword" placeholder="Ingresa tu contraseña" required v-model="contrasena"/>
      </div>
      <div class="mb-3">
        <label for="direccionInput" class="form-label" name="direccionuser">Direccion:
        </label>
        <input type="text" id="direccionInput" class="form-control" placeholder="Ingresa tu direccion" required v-model="direccion"/>
      </div>
      <div class="mb-3">
        <label for="barrioInput" class="form-label" name="barriouser">Barrio:
        </label>
        <input type="text" id="barrioInput" class="form-control" placeholder="Ingresa tu barrio" required v-model="barrio"/>
      </div>

      <div class="button-box">
        <button type="submit" class="btn" id="guardar" name="guardar">
          Guardar
        </button>
        <!-- <button type="button" class="btn" id="eliminar" name="eliminar"  @click="eliminar"> Eliminar</button> -->
          <button type="button" class="btn"  id="actualizar" name="actualizar" @click="actualizar">Actualizar</button>
          <button type="button" id="consultar" name="consultar"     class="btn btn-primary" @click="consultar">Consultar</button>
      </div>
    </form>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      id_usuario:"",
      nombres: "",
      apellidos: "",
      tipo_documento:"",
      nDocumento:"",
      telefono:"",
      pais:"",
      ciudad:"",
      correo:"",
      username: "",
      contrasena:"",
      direccion:"",
      barrio: "",

    };
  },

  methods: {
    guardar() {
      axios
        .post("http://localhost:8080/api/usuarios", {

       nombres:this.nombres,
      apellidos:this.apellidos,
      tipo_documento:this.tipo_documento,
      nDocumentor:this.nDocumento,
      telefono:this.telefono,
      pais:this.pais,
      ciudad:this.ciudad,
      correo:this.correo,
      username:this.username,
      contrasena:this.contrasena,
      direccion:this.direccion,
      barrio: this.barrio,
        })

        .then((response) => {
          console.log("Registrado con éxito:", response.data);
          alert("exito");
          location.reload();
          this.$router.go(0);
          this.nombreuser="";
          this.apellidouser="";
          this.tipodocumuser="";
          this.ndocumuser="";
          this.teluser="";
          this.pais_user="";
          this.ciudad_user="";
          this.correo_user="";
          this.nomusuariouser="";
          this.passwuser="";
          this.direccionusername="";
          this.barrio="";


        })
        .catch((error) => {
          console.error("Error al registrar usuario:", error);
        });
    },
    consultar() {
      
      axios
        .get('http://localhost:8080/api/usuarios/'+this.id_usuario)
        .then((response) => {
          // Actualizar los campos del formulario con los datos del estudiante consultado
         
          this.nombres=response.data.nombres;

          this.apellidos=response.data.apellidos;
          this.tipo_documento=response.data.tipo_documento;
          this.nDocumento=response.data.nDocumento;
          this.telefono=response.data.telefono;
          this.pais=response.data.pais;
          this.ciudad=response.data.ciudad;
          this.correo=response.data.correo;
          this.username=response.data.username;
          this.contrasena=response.data.contrasena;
          this.direccion=response.data.direccion;
          this.barrio=response.data.barrio;
        })
        .catch((error) => {
          console.error("Error al consultar estudiante:", error);
        });
    },
    actualizar() {
      
      axios
        .put("http://localhost:8080/api/usuarios/actualizar/"+this.id_usuario, {
          
       nombres:this.nombres,
      apellidos:this.apellidos,
      tipo_documento:this.tipo_documento,
      nDocumentor:this.nDocumento,
      telefono:this.telefono,
      pais:this.pais,
      ciudad:this.ciudad,
      correo:this.correo,
      username:this.username,
      contrasena:this.contrasena,
      direccion:this.direccion,
      barrio: this.barrio,
      
        })
        .then((response) => {
          location.reload()
          this.$router.go(0)
          console.log("Estudiante actualizado con éxito:", response.data);
        })
        .catch((error) => {
          console.error("Error al actualizar estudiante:", error);
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

.button-box{
  display: grid;
  height: 20%;
  grid-template-columns: repeat(3, 1fr);
  grid-column-gap: 10%;
  margin-inline: 10%;
  margin-left: 4%;
  margin-top: 10%;
  
}
.button-box .btn {
  margin-top: 5%;
  color: rgb(253, 252, 252);
  background-color: rgb(107, 107, 219);
}
</style>
