<template>
<div class="row">
<div class="prueba" >
    <h1>Museos de la ciudad de Madrid </h1>
     <div class="container">
       <div class="row">
        <form class="d-flex">  
          <select class="form-select" v-model="event" @change="verSeleccionado">
            <option value="">--Selecciona una opción--</option>
            <option v-for="(event,i) in eventos" :key="i" :value="event['@id']"> {{event['title']}} </option>
          </select>
        </form>
       </div>
     </div>
  
    <div class="clearfix">
      <img src="../assets/museo1.jpg" class="col-md-6 float-md-end mb-3 ms-md-3" alt="">
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
        <span>Ubicacion: </span>{{informacion.datos['location']}} <br>
      </p>
      <p style="text-align: left">
        <span >Descripción: </span>{{informacion.datos.organization['organization-desc']}} <br>
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
  name: "Testapi",
  props: {},
  setup() {
    let eventos = reactive([]);
    let event = ref("");
    let informacion = reactive([]);
   

    //API Museo

    // fetch('https://datos.madrid.es/egob/catalogo/300107-0-agenda-actividades-eventos.json')
    fetch("https://datos.madrid.es/egob/catalogo/201132-0-museos.json")
      // fetch('https://datos.madrid.es/egob/catalogo/206974-0-agenda-eventos-culturales-100.json')

      .then((res) => {
        return res.json();
      })
      .then((datos) => {
        console.log(datos["@graph"]);
        // eventos.value=datos
        datos["@graph"].forEach((element) => {
          eventos.push(element);
        });
      });

    function verSeleccionado() {
      console.log(event.value);

      fetch(event.value)
        .then((res) => res.json())
        .then((info) => {
          console.log(info["@graph"][0]);
          informacion.datos = info["@graph"][0];
        });
    }



    return {
      eventos,
      event,
      verSeleccionado,
     informacion, 
     
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