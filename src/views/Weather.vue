<template>
  <div class="prueba">

    <TestWeather/>
    <Map />
  </div>
</template>

<script>
// @ is an alias to /src

import TestWeather from '../components/TestWeather.vue'

export default {
  name: 'Weather',
  components: {
    TestWeather
  }
}
</script>