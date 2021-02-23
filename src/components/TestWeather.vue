<template>
  <div class="prueba" >
      <h1>
         El tiempo en los municipios de España
      </h1>
      <select>
          <option v-for="(prov,i) in provincias" :key="i">
              {{prov}}
          </option>
      </select>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'
export default {

    name: 'TestWeather',
    props: {},
    setup(){
        let provincias= []
        fetch('https://datos.madrid.es/egob/catalogo/200761-0-parques-jardines.json')
            .then(res=>res.json())
            .then(datos=>{
                // console.log(datos.response.docs[0])
            })

            return {
                provincias
            }
    }

}
</script>

<style>

</style>