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
      
      this.tareas = [...this.tareas, tarea]
    },

    deleteTask(id) {
      console.log(id);
      //Se comprueba que id recibe el boton con el console.log
      //Se cambia el metodo filter por el splice, ya que el filter comparaba el id recibido que es el del array
      // con el id introducido a mano, por lo que eliminaba lo que le apetecia y no lo que queriamos.
      //de esta manera le indicamos que elimine el id del array que es el que nos interesa.
      this.tareas.splice(id,1);
      // this.tareas = this.tareas.filter( tarea => tarea.id !== id)

      //El filter esta bien pero si cambiamos el codigo para que el id lo inyecte directamente por logica no a mano
      //porque de la manera que lo tenemos no se va a corresponder con su posicion en el array.

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
