<script>
import navBar from '../components/navBar.vue'
export default {
  data() {
    return {
      All: true,
      Food: false,
      NonFood: false,
      Fashone: false
    }
  },
  components: {
    navBar
  }
}
</script>
<template>
  <div>
    <v-container fluid class="top-0 position-absolute left-0">
      <navBar />
      <v-row>
        <v-col cols="11" class="d-flex justify-end">
          <v-btn
            variant="text"
            :color="All ? 'orange' : 'gray'"
            @click="
              (this.All = !this.All) &&
                (this.Food = false) &&
                (this.Fashone = false) &&
                (this.NonFood = false)
            "
            >All</v-btn
          >
          <v-btn
            variant="text"
            :color="Food ? 'orange' : 'gray'"
            @click="
              (this.Food = !this.Food) &&
                (this.Fashone = false) &&
                (this.NonFood = false) &&
                (this.All = false)
            "
            >Food</v-btn
          >
          <v-btn
            variant="text"
            :color="NonFood ? 'orange' : 'gray'"
            @click="
              (this.Food = false) &&
                (this.Fashone = false) &&
                (this.NonFood = this.NonFood) &&
                (this.All = false)
            "
            >Non Food</v-btn
          >
          <v-btn
            variant="text"
            :color="Fashone ? 'orange' : 'gray'"
            @click="
              (this.Food = false) &&
                (this.Fashone = !this.Fashone) &&
                (this.NonFood = false) &&
                (this.All = false)
            "
          >
            Fashon & Linen</v-btn
          >
        </v-col>
      </v-row>

      
      <v-row>
        <v-col cols="6" class="d-flex justify-center">
          <!-- {{ items.length }} -->
          <span> products</span>
          <v-btn variant="text"><v-icon>mdi-table</v-icon></v-btn
          ><v-btn variant="text"><v-icon>mdi-table</v-icon></v-btn>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
