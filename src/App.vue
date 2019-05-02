<template>
  <div class="container">
    <DecksList/>
  </div>
</template>

<script>
import DecksList from "./components/DecksList.vue";

export default {
  name: "app",
  components: {
    DecksList
  }
}
</script>
<style>
body {
  background-color: #2f3542;
}
</style>

