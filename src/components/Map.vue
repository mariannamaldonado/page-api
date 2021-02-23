<template>
  <div class="map">
      <h1>Mapa</h1>
    <div id="mapid"></div>
  </div>
</template>

<script>
import L from "leaflet"
import { onMounted} from 'vue'

export default {
  name: 'Map',
    props: {},
setup(){
    let mymap

    onMounted(()=>{
        mymap=L.map('mapid').setView([51.505, -0.09],13)

    L.tileLayer('https://{s}.tile.openstreetmap.fr/hot/{z}/{x}/{y}.png', {
	maxZoom: 19,
	attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, Tiles style by <a href="https://www.hotosm.org/" target="_blank">Humanitarian OpenStreetMap Team</a> hosted by <a href="https://openstreetmap.fr/" target="_blank">OpenStreetMap France</a>'
}).addTo(mymap)

    })
  
    return{

    }
  }
}
</script>

<style>
#mapid { height: 180px }

</style>