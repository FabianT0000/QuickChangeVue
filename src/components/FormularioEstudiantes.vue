<template>
  <div class="container">
    <h1>Formulario de Estudiante</h1>
    <form id="student-form" @submit.prevent="guardar">
      <div class="form-group">
        <label for="codigo">Código:</label>
        <input type="text" id="codigo" name="codigo" required  v-model="codigo" />
      </div>
      <div class="form-group">
        <label for="nombre">Nombre:</label>
        <input type="text" id="nombre" name="nombre1" required v-model="nombre"/>
      </div>
      <div class="form-group">
        <label for="apellido">Apellido:</label>
        <input type="text" id="apellido" name="apellido" required v-model="apellido"/>
      </div>
      <div class="form-group">
        <label for="edad">Edad:</label>
        <input type="number" id="edad" name="edad" required v-model="edad" />
      </div>

      <button type="submit" id="guardar" name="guardar">Guardar</button><br />
      <button type="button" id="eliminar" name="eliminar" @click="eliminar"> Eliminar</button ><br />
      <button type="button" id="actualizar" name="actualizar"  @click="actualizar"> Actualizar</button><br />
      <button type="button" id="consultar" name="consultar" @click="consultar"> Consultar</button><br />
    </form>
  </div>
</template>

<script>
import axios from "axios";

export default {
  
  data() {

    return {
      codigo: "",
      nombre: "",
      apellido: "",
      edad: null,
    };

  },

  methods: {
    guardar() {
      
      axios
        .post("http://localhost:8080/api/estudiantes", {
          // codigo: this.codigo,
          // nombre: this.nombre,
          // apellido: this.apellido,
          // edad: this.edad,
        })
        .then((response) =>
         {
          console.log("Estudiante registrado con éxito:", response.data);
          alert("exito");
          location.reload()
          this.$router.go(0)
          
        this.codigo = '';
        this.nombre = '';
        this.apellido = '';
        this.edad = '';
         
        })
        .catch((error) => {
          console.error("Error al registrar estudiante:", error);
        });
       
    },
    
    consultar() {
      
      axios
        .get('http://localhost:8080/api/estudiantes/'+this.codigo)
        .then((response) => {
          // Actualizar los campos del formulario con los datos del estudiante consultado
          this.nombre = response.data.nombre;
          this.apellido = response.data.apellido;
          this.edad = response.data.edad;
        })
        .catch((error) => {
          console.error("Error al consultar estudiante:", error);
        });
    },


    actualizar() {
      
      axios
        .put("http://localhost:8080/api/estudiantes/actualizar/"+this.codigo, {
          codigo:this.codigo,
          nombre: this.nombre,
          apellido: this.apellido,
          edad: this.edad,
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
    eliminar() {
     
      axios
        .delete("http://localhost:8080/api/estudiantes/"+this.codigo)
        .then(() => {
          console.log("Estudiante eliminado con éxito");
          // Limpiar los campos del formulario después de eliminar
          this.codigo = "";
          this.nombre = "";
          this.apellido = "";
          this.edad = null;
          location.reload()
          this.$router.go(0)
        })
        .catch((error) => {
          console.error("Error al eliminar estudiante:", error);
        });
    },
  },
};
</script>
