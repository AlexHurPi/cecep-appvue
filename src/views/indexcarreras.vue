<template>      
    <div class="container">
        <h1>Listado Carreras </h1>    
<table class="table">
    <thead>
        <tr>
            <th scope="col">#</th>
            <th scope="col">Id</th>
            <th scope="col">Nombre</th>
            <th scope="col">Observacion</th>       
        </tr>
    </thead>
    <tbody>
        
        <tr v-for="(carrera,index)in carreras" :key="index">
            <th scope="row">{{ index + 1 }}</th>
            <td>{{ carrera.id }}</td>
            <td>{{ carrera.nombre }}</td>
            <td>{{ carrera.observacion }}</td>                      
        </tr>
      </tbody>
     </table>
    </div>
</template>
<script>
import axios from 'axios'

export default {

    name: 'Carrera',
    data(){
        return{
            carreras: []
        }
   },
   mounted() {
        axios
            .get('http://127.0.0.1:8000/api/carreras')
                 .then(response =>(this.carreras=response.data.carreras))
                        
            },
    }
                 
</script>