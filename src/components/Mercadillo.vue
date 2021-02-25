<template>
<div class="row">
<div class="prueba" >

<!-- inicio Mercadillo -->
    <h1>Mercadillos en la via publica </h1>
      <div class="container">
       <div class="row">
        <form class="d-flex">  
          <select class="form-select" v-model="mercado" @change="verSeleccionado">
            <option value="">--Selecciona una opción--</option>
            <option v-for="(mercado,i) in market" :key="i" :value="mercado['@id']"> {{mercado['title']}} </option>
          </select>
        </form>
       </div>
     </div>

      <div class="clearfix">
      <img src="../assets/mercadillo.jpg" class="col-md-6 float-md-end mb-3 ms-md-3" alt="">
    <div class="informacion" v-if="informacion.datos">
      <h4 class="d-flex justify-content-center text-align-center"> {{informacion.datos.title}}:</h4>
      <p style="text-align: left">
        <span>Lugar: </span>{{informacion.datos['address']['locality']}} <br>
      </p>
      <p style="text-align: left">
        <span>Codigo postal: </span>{{informacion.datos['address']['postal-code']}} <br>
      </p>
      <p style="text-align: left">
        <span style="text-align: left">Dirección: </span>{{informacion.datos['address']['street-address']}} <br>
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
  name: "Mercadillo",
  props: {},
  setup() {
  
    let market = reactive([])
    let mercado =ref("")
    let informacion =reactive([])

    //  // API MERCADILLOS
    fetch("https://datos.madrid.es/egob/catalogo/202105-0-mercadillos.json")

      .then((res) => {
        return res.json();
      })
      .then((datos) => {
        console.log(datos["@graph"]);
        // market.value=datos
        datos["@graph"].forEach((element) => {
          market.push(element);
        });
      });

    function verSeleccionado() {
      console.log(mercado.value);

      fetch(mercado.value)
        .then((res) => res.json())
        .then((info) => {
          console.log(info["@graph"][0]);
          informacion.datos = info["@graph"][0];
        });
    }

    return {

      market, mercado, verSeleccionado, informacion
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