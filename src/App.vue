<template>
  <div class="container" id="app">
    <tareas v-bind:tareas = "tareas"/>
    <hr>
    <formularioTareas @enviarTarea="agregarTarea"/>
  </div>
</template>

<script>
import tareas from "./components/tareas";
import formularioTareas from "./components/formulario";
export default {
  name: "App",
  components: {
    tareas,
    formularioTareas

  },
  data() {
    return {
      tareas: [
        {
          id: 1,
          nombre: "lectura",
          tiempo: "1 hora",
          colaborador: "Felicidad",
        },
        {
          id: 2,
          nombre: "poner la lavadora",
          tiempo: "1,5 horas",
          colaborador: "Colon",
        },
        {
          id: 3,
          nombre: "hacer cookies",
          tiempo: "2 hora",
          colaborador: "Colesterol",
        },
      ],
    };
  },

  methods:{
    agregarTarea(tarea){
      this.tareas = [
        this.tareas,
        tarea
      ]
    }    
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
