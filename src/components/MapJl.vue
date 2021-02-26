<template>
  <div class="map">
    <div id="mapid"></div>
    <div class="toolbar">
      <button class="btn btn-primary" @click="markerMiCasa">Marcador de mi casa</button> 
      <button class="btn btn-primary" @click="circleMiCasa">Circulo de mi casa</button> 
      <button class="btn btn-primary" @click="popUpMiCasa">PopUp de mi casa</button>      
    </div>
  </div>

</template>


<script>
import L from "leaflet"
import { onMounted } from 'vue'
export default {
  setup(){
    //variable para representar el objeto MAPA
    let mymap
    let marker
    onMounted(()=>{
      mymap=L.map(mapid).setView([40.30505797514754, -3.931373193814625], 18)
      L.tileLayer('https://stamen-tiles-{s}.a.ssl.fastly.net/watercolor/{z}/{x}/{y}.{ext}', {
        attribution: 'Map tiles by <a href="http://stamen.com">Stamen Design</a>, <a href="http://creativecommons.org/licenses/by/3.0">CC BY 3.0</a> &mdash; Map data &copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
        subdomains: 'abcd',
        minZoom: 1,
        maxZoom: 16,
        ext: 'jpg'
      }).addTo(mymap)
      mymap.on('click', verInfo)
    })
    function verInfo(e){
      alert(e.latlng)
      console.log(e)
    }
    function markerMiCasa(){
      marker=L.marker([40.30538525158257, -3.929763868391571]).addTo(mymap)
    }
    function circleMiCasa(){
      L.circle([40.30538525158257, -3.929763868391571], {
          color: 'red',
          fillColor: '#f03',
          fillOpacity: 0.3,
          radius: 500
      }).addTo(mymap)
    }
    function popUpMiCasa(){
      //marker.bindPopup("<b>Hello world!</b><br>I am a popup.").openPopup()
      var popup = L.popup()
        .setLatLng([40.30538525158257, -3.929763868391571])
        .setContent("Estoy aquí")
        .openOn(mymap)
    }
    return {
      markerMiCasa,
      circleMiCasa,
      popUpMiCasa
    }
  }
}
</script>

<style lang="scss" scoped>
  .map{
  }
  .toolbar{
    padding:10px;
    text-align: left;
    button{
      margin-right: 10px;
    }
  }
  #mapid { height: 500px; }
</style>