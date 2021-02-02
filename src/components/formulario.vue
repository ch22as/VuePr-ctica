<template>
    <div id="formularioTareas">
        <form @submit.prevent="enviarFormulario">
            <div class="container">
                <div class="row">
                    <div class="col-md-4">
                        <div class="form-group">
                            <label class="form-label" for="">nombre</label>
                            <input class="form-control" type="text" v-model="tarea.nombre">
                        </div>

                        <div class="form-group">
                            <label class="form-label" for="">tiempo</label>
                            <input class="form-control" type="text" v-model="tarea.tiempo">
                        </div>

                        <div class="form-group">
                            <label class="form-label" for="">colaborador</label>
                            <input class="form-control" type="text" v-model="tarea.colaborador">

                            <input class="btn btn-primary" type="button" value="boton">
                        </div>
                    </div>
                </div>
            </div>
        </form>

    </div>
    
</template>
<script>
export default {
    name: '#formularioTareas',
    
    data(){
        return{
            tarea:{
                nombre:'',
                tiempo:'',
                colaborador:''
            }
        }
    },

    methods: {
        enviarFormulario(){
            this.$emit('agregarTarea', this.tarea);
            console.log("Formulario enviado");
        }
    }
}
</script>
