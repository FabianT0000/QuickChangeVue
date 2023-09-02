<template>
    <div class="container">
        <h1>Tabla de Estudiantes</h1>
        <table>
            <thead>
                <tr>
                    <th>Código</th>
                    <th>Nombre</th>
                    <th>Apellido</th>
                    <th>Edad</th>
                    
                </tr>
            </thead>
            <tbody>
              
                    <tr v-for="estudiante in estudiantes" :key="estudiante.codigo">
                    <td>{{ estudiante.codigo }}</td>
                    <td>{{ estudiante.nombre }}</td>
                    <td>{{ estudiante.apellido }}</td>
                    <td>{{ estudiante.edad }}</td>
                </tr>
                   
                <router-view />
            
              
            </tbody>
        </table>
    </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      estudiantes: [],
    };
  },
  methods: {
    obtenerEstudiantes() {
      // Método para obtener la lista de todos los estudiantes
      axios.get("http://localhost:8080/api/estudiantes/listar")
      .then((response) => {
        this.estudiantes = response.data;
      })
      .catch((error) => {
        console.error("Error al obtener estudiantes:", error);
      });
    },
  },
  mounted() {
    // Llamar al método para obtener la lista de estudiantes al cargar el componente
    this.obtenerEstudiantes();
  },
};
</script>
