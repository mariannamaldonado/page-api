<template>
  <div class="prueba">

    <Testapi/>
    <Map/>
  </div>
</template>

<script>
// @ is an alias to /src

import Testapi from '../components/Testapi.vue'

export default {
  name: 'Test',
  components: {
    Testapi
  }
}
</script>