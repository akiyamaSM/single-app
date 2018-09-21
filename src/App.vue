<template>
  <div id="app">
    <Rate :stars="2" :maxstars="5" name="my-field" id="my-id-field" />
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
