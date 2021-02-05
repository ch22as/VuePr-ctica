<template>
    <div id="tablaTareas">
        <table class="warning">
            <thead>
                <tr>
                    <th>Id</th>
                    <th>Tarea</th>
                    <th>Tiempo</th>
                    <th>Colaborador</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(tarea, index) in tareas" :key="index">
                    <td>{{tarea.id}}</td>
                    <td>{{tarea.nombre}}</td>
                    <td>{{tarea.tiempo}}</td>
                    <td>{{tarea.colaborador}}</td>
                    <td>
                        <input @click="$emit('deleteTask', index)" class="btn btn-danger" type="" value="Borrar">
                    </td>
                </tr>

                <tr>
                    <td><input class="btn btn-primary" type="submit" value="boton"></td>
                </tr>
            </tbody>
        </table>

    </div>
</template>
<script>
export default {
    name : "#tablaTareas",
    props: ['tareas']
}
</script>

<style scoped>
    tbody{
        background-color: aliceblue;
    }


</style>