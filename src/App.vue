<template>
  <div id="app">
   <appweather></appweather>
  </div>
</template>

<script>
import weather from './components/Weather.vue'

export default {
  name: 'app',
  components: {
    appweather: weather
  }
}
</script>

<style>

</style>
