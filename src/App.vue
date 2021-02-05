<template>
  <div class="container" id="app">
    <tareas v-bind:tareas = "tareas" @deleteTask="deleteTask" />
    <hr>
    <formularioTareas @agregarTarea="agregarLinea" />
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
    agregarLinea(tarea){
      /* let id = 0;
      if (Object.keys(this.tarea).length > 0) {
        id = this.tarea[this.tareas.length - 1].id + 1;
      } */
      this.tareas = [...this.tareas, tarea]
    },

    deleteTask(id) {
      this.tareas = this.tareas.filter( tarea => tarea.id !== id)
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
