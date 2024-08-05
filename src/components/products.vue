<!-- eslint-disable vue/multi-word-component-names -->
<script>
export default {
  props: {
    styleDesign: Boolean
  },
  data() {
    return {
      prod: [
        {
          id: 1,
          name: 'Spinneys Value Sponge For Glass Cookware',
          price: 3.95,
          img: 'https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/2/328465.jpg?format=webp'
        },
        {
          id: 2,
          name: 'Spinneys Black Eyed peas, 500Gm',
          price: 14.25,
          img: 'https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/5/356385.jpg?format=webp'
        },
        {
          id: 3,
          name: 'Abu Auf - Cinnamon Sticks - 1Kg',
          price: 34.95,
          img: 'https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/5/359090.jpg?format=webp'
        },
        {
          id: 4,
          name: 'Spinneys Value Scouring Sponge Grooved- 3Pcs ',
          price: 75.95,
          img: 'https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/2/328464.jpg?format=webp'
        },
        {
          id: 5,
          name: 'Spinneys Supreme Aluminum Foil Multi Purpose- 40 Cm',
          price: 15.95,
          img: 'https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/2/328781.jpg?format=webp'
        },
        {
          id: 6,
          name: 'Class A Stroopwafel Chocolate Waffle - 30 Gr ',
          price: 34.95,
          img: ' https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/2/324786_1.jpg?format=webp'
        }
      ]
    }
  }
}
</script>
<template>
  <div class="app">
    <v-container fluid class="ma-auto">
      <v-row
        class="pa-2"
        style="gap: 40px; margin-left: 5%"
        :style="{ display: styleDesign ? 'flex' : 'block' }"
      >
        <v-card
          v-for="item in prod"
          :key="item.id"
          width="220"
          elevation="0"
          style="min-height: 250px"
        >
          <RouterLink to="/informationProduct">
            <div class="text-end"><v-icon color="#03714d">mdi-heart-outline</v-icon></div>
            <div class="text-center">
              <img :src="item.img" alt="" width="150" height="150" />
            </div>
            <div>
              <v-card-text style="min-height: 75px">{{ item.name }}</v-card-text>
              <div class="pl-4">
                <p style="color: #03714d; font-weight: 600">EGP: {{ item.price }}</p>
                <button
                  style="
                    position: relative;
                    width: 50%;
                    border: 1px solid rgb(3, 113, 77);
                    border-radius: 14px;
                  "
                >
                  Add to cart
                  <v-badge
                    color="rgb(251 206 0) "
                    content="1"
                    style="position: absolute; right: 1%; color: green"
                  ></v-badge>
                </button>
              </div>
            </div>
          </RouterLink>
        </v-card>
      </v-row>
    </v-container>
  </div>
</template>
