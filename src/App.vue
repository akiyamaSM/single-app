<template>
  <div id="app">
    <Rate :stars="2" :maxstars="5" name="my-field" id="my-id-field" color="#20152f" />
  </div>
</template>

<script>
import Rate from './components/Rate.vue'

export default {
  name: 'app',
  components: {
    Rate
  }
}
</script>

<style>

</style>
