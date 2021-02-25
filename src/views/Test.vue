<template>
  <div class="prueba">

    <Testapi/>
    <Mercadillo/>
    <Parques/>
    
    
    <Map/>
  </div>
</template>

<script>
// @ is an alias to /src

import Testapi from '../components/Testapi.vue'
import Mercadillo from '../components/Mercadillo.vue'
import Parques from '../components/Parques.vue'

export default {
  name: 'Test',
  components: {
    Testapi,
    Mercadillo,
    Parques
  }
}
</script>