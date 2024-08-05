<script>
export default {
  data() {
    return {
      overlay: true
    }
  }
}
</script>
<template>
  <div
    class="position-fixed right-0 h-screen top-0 pa-5"
    style="background-color: aliceblue; width: 5% !important"
  >
    <v-badge
      color="error"
      content="2"
      style="position: absolute; left: 50%; transform: translateX(-50%)"
    >
      <v-icon @click="overlay = true" color="rgb(3, 113, 77)" style="font-size: 25px"
        >mdi-cart</v-icon
      >
    </v-badge>

    <v-overlay v-model="overlay">
      <v-card style="width: 250px; height: 100vh; right: 0; position: absolute">
        <v-card-text> khalec </v-card-text>
      </v-card>
    </v-overlay>
  </div>
</template>
