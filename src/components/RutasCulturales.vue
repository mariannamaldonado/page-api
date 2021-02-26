<template>
<div class="row">
<div class="prueba" >

<!-- inicio Mercadillo -->
    <h1>Rutas culturales para personas mayores</h1>
      <div class="container">
       <div class="row">
        <form class="d-flex">  
          <select class="form-select" v-model="cultura" @change="verSeleccionado">
            <option value="">--Selecciona una opción--</option>
            <option v-for="(cultura,i) in culturales" :key="i" :value="cultura.destino_denominacion"> {{cultura['destino_denominacion']}} </option>
          </select>
        </form>
       </div>
     </div>

      <div class="clearfix">
      <img src="../assets/almendros.jpg" class="col-md-6 float-md-end mb-3 ms-md-3" alt="">
    <div class="informacion" v-if="informacion.datos">
      <h4 class="d-flex justify-content-center text-align-center"> {{informacion.datos.destino_denominacion}}:</h4>
      <p style="text-align: left">
        <span>Lugar: </span>{{informacion.datos.destino_denominacion}} <br>
      </p>
      <p style="text-align: left">
        <span>Codigo postal: </span>{{informacion.datos['empresa_denominacion']}} <br>
      </p>
      <p style="text-align: left">
        <span style="text-align: left">Dirección: </span>{{informacion.datos['destino_precio']}} <br>
      </p>
      <p style="text-align: left">
        <span>Horario: </span>{{informacion.datos.organization['schedule']}} <br>
      </p>
       <p style="text-align: left">
        <span>Localización: </span>{{informacion.datos.organization['location']}} <br>
      </p>
      <p style="text-align: left">
        <span >Accesibilidad: </span>{{informacion.datos.organization['organization-desc']}} <br>
      </p>
      <p style="text-align: left">
        <span>Servicios: </span>{{informacion.datos.organization['services']}}<br>
      </p>
    </div>
    </div>
</div>
</div>
</template>

<script>
import { ref, reactive } from "vue";

export default {
  name: "RutasCulturales",
  props: {},
  setup() {
  
    let culturales = reactive([])
    let  cultura =ref("")
    let informacion =reactive([])
    let datos=reactive({})

    //  // API MERCADILLOS
    fetch("https://datos.comunidad.madrid/catalogo/dataset/1ff1f579-6a2d-4356-a244-34a2c0ad3fa4/resource/23294b86-d813-4487-905d-7d1c4f97d191/download/rutas_culturales_personas_mayores.json")

       .then((res) => {
        return res.json();
      })
      .then((datos) => {
        console.log(datos["data"]);
        // market.value=datos
        datos["data"].forEach((element) => {
          culturales.push(element);
        });
      });
    function verSeleccionado() {
      console.log(cultura.value);

      fetch(cultura.value)
        .then((res) => res.json())
        .then((info) => {
          console.log(info["data"][0]);
          informacion.datos = info["data"][0];
        });
    }

    return {

      culturales, cultura, verSeleccionado, informacion
    }

 
 
  }
}
</script>

<style>
.row {
  display: flex;
  margin: 50px;
}

</style>