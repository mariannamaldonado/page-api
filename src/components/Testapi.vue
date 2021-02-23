<template>
<div class="row">
<div class="prueba" >
    <h1>Agenda de actividades y eventos </h1>
    <!-- //inicio container -->
    
  <div class="container">
    <div class="row">
      <div class="col">
        <!-- inicio -->
        <form class="d-flex">  
          <select class="form-select" v-model="event" @change="verSeleccionado">
            <option value="">--Selecciona una opción--</option>
            <option v-for="(event,i) in eventos" :key="i" :value="event['@id']"> {{event['title']}} </option>
          </select>
        </form>

        <div class="informacion" v-if="informacion.datos">
          <div class="card text-center">
            <div class="card-header">
              <h4 class="d-flex justify-content-center text-align-center"> {{informacion.datos.title}}:</h4>
            </div>
            <div class="card-body">
              <h5 class="card-title">
                <span>Lugar: </span>{{informacion.datos['address']['locality']}} <br>
              </h5>
              <p class="card-text">
                <span>Codigo postal: </span>{{informacion.datos['address']['postal-code']}} <br>.
                <span>Dirección: </span>{{informacion.datos['address']['street-address']}} <br>
                <span>Horario: </span>{{informacion.datos.organization['schedule']}} <br>
                <span>Descripción: </span>{{informacion.datos.organization['organization-desc']}} <br>
                <span>Servicios: </span>{{informacion.datos.organization['services']}}<br>
              </p>
              <a href="#" class="btn btn-primary">Ir al mapa</a>
            </div>
            <div class="card-footer text-muted">
             2 days ago
            </div>
          </div>
        </div>
      </div>
     <!-- fin -->
    </div>
  </div>

     <!-- //fin container  -->

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

    //API AGENDA EVENTOS CULTURALES

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
    };
  },
};
</script>

<style>
.row {
  display: flex;
  margin: 50px;
}
</style>