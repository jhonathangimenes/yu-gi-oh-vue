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
  background-color: #576574;
}
.container {
  background-color: #2f3542!important;
  margin-top: 30px;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 5px 5px 5px #222f3e;
}
</style>

