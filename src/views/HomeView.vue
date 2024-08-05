<script>
import navBar from '../components/navBar.vue'
import products from '@/components/products.vue'
export default {
  data() {
    return {
      stylerow: true,
      btnNames: [
        { id: 1, textBtn: 'All', status: true },
        { id: 2, textBtn: 'Food', status: false },
        { id: 3, textBtn: 'Fashion& Linen', status: false },
        { id: 4, textBtn: 'Non-Food', status: false }
      ]
    }
  },
  components: {
    navBar,
    products
  },
  methods: {
    updateStatus(id) {
      this.btnNames.forEach((btn) => {
        btn.status = btn.id === id
      })
    }
  }
}
</script>
<template>
  <div>
    <navBar />
    <v-container fluid class="top-0 position-absolute left-0" style="width: 95%">
      <v-row
        justify="center"
        style="margin-top: 80px !important; padding-bottom: 40px; border-bottom: 1px solid gray"
      >
        <v-btn
          v-for="n in btnNames"
          :key="n.id"
          :variant="n.status ? 'elevated' : 'text'"
          :color="n.status ? '#ff6100' : 'black'"
          :style="{ color: n.status ? 'white' : 'black' }"
          style="font-size: 10px"
          @click="updateStatus(n.id)"
        >
          {{ n.textBtn }}
        </v-btn>
      </v-row>

      <v-row>
        <span> products</span>
        <v-btn variant="text" @click="stylerow = true" :color="stylerow ? '03714d' : 'black'"
          ><v-icon>mdi-table-row</v-icon></v-btn
        >
        <v-btn variant="text" @click="stylerow = false" :color="stylerow ? 'black' : '03714d'"
          ><v-icon>mdi-table-column</v-icon></v-btn
        >
      </v-row>
      <products :styleDesign="stylerow" />
    </v-container>
  </div>
</template>
