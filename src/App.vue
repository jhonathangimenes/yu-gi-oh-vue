<template>
  <div class="container">
    <CardsList/>
  </div>
</template>

<script>
import CardsList from './components/CardsList.vue'

export default {
  name: 'app',
  components: {
    CardsList
  }
}
</script>
<style>
  body {
    background-color: #2f3542;
  }
</style>

