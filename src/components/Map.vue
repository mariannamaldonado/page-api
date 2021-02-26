<template>
  <div class="map">
      <h1>Mapa</h1>
    <div id="mapid"></div>
    <div class="toolbar">
      <button class="btn btn-primary" @click="markerMuseoPrado">Museo del Prado</button> 
      <button class="btn btn-primary" @click="circleParque">Circulo Parque Quinta de los Molinos</button> 
      <button class="btn btn-primary" @click="popUpMercadillo">PopUp Mercadillo El Rastro</button>      
    </div>
  </div>

</template>

<script>
import L from "leaflet"
import { onMounted } from 'vue'

export default {
  // name: 'Map',
  //   props: {},
setup(){
    let mymap
    let marker

    onMounted(()=>{
        mymap=L.map(mapid).setView([40.30505797514754, -3.931373193814625], 18)

L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}', {
	attribution: 'Tiles &copy; Esri &mdash; Source: Esri, i-cubed, USDA, USGS, AEX, GeoEye, Getmapping, Aerogrid, IGN, IGP, UPR-EGP, and the GIS User Community'
}).addTo(mymap)
  mymap.on('click', verInfo)
    })
  function verInfo(e){
      alert(e.latlng)
      console.log(e)
    }
    function markerMuseoPrado(){
      marker=L.marker([40.4137818, 40.44245748722783]).addTo(mymap)
    }
    function circleParque(){
      L.circle([40.431900, -3.656881], {
          color: 'red',
          fillColor: '#f03',
          fillOpacity: 0.3,
          radius: 500
      }).addTo(mymap)
    }
    function popUpMercadillo(){
      //marker.bindPopup("<b>Hello world!</b><br>I am a popup.").openPopup()
      var popup = L.popup()
        .setLatLng([40.408623, -3.707338])
        .setContent("El Rastro")
        .openOn(mymap)
    }
    return {
      markerMuseoPrado,
      circleParque,
      popUpMercadillo
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
#mapid { height: 350px }

</style>