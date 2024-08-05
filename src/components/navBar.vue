<script>
export default {
  data() {
    return {
      overlay: false,
      prod: [
        {
          id: 1,
          name: 'Spinneys Value Sponge For Glass Cookware',
          price: 3.95,
          img: 'https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/2/328465.jpg?format=webp',
          count: 1
        },
        {
          id: 2,
          name: 'Spinneys Black Eyed peas, 500Gm',
          price: 14.25,
          img: 'https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/5/356385.jpg?format=webp',
          count: 1
        },
        {
          id: 3,
          name: 'Abu Auf - Cinnamon Sticks - 1Kg',
          price: 34.95,
          img: 'https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/5/359090.jpg?format=webp',
          count: 1
        },
        {
          id: 4,
          name: 'Spinneys Value Scouring Sponge Grooved- 3Pcs ',
          price: 75.95,
          img: 'https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/2/328464.jpg?format=webp',
          count: 1
        }
      ]
    }
  },
  methods: {
    incrementCount(button) {
      button.count++
    },
    decrementCount(button) {
      if (button.count > 1) {
        button.count--
      }
    }
  }
}
</script>
<template>
  <div
    class="position-fixed right-0 h-screen top-0 pa-5"
    style="background-color: #eaeaea; width: 5% !important; z-index: 1000"
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
      <v-card class="fixed-card" style="width: 50vw; height: 100vh; position: relative; left: 100%">
        <v-btn variant="text" @click="overlay = false" class="my-2">
          <v-icon>mdi-close</v-icon>
        </v-btn>
        <hr />
        <v-card-text class="d-flex justify-space-between ma-4">
          <span>Subtotal</span>
          <span>697.29 Egp</span>
        </v-card-text>
        <div class="text-center">
          <v-btn
            size="small"
            class="h-auto py-2"
            style="
              color: white;
              width: 50%;
              background: linear-gradient(45deg, #0a6c4b, #8cb114);
              border-radius: 15px;
            "
            >Checkout</v-btn
          >
          <hr style="margin: 10px 0px" />
        </div>
        <div v-for="n in prod" :key="n.id" class="d-flex flex-column border-b mb-5 pb-2">
          <div class="d-flex">
            <img :src="n.img" alt="" width="100" height="100" />
            <div class="flex-grow-1 mr-4">
              <div>
                <p>{{ n.name }}</p>
                <p style="color: #03714d; font-weight: 600">EGP: {{ n.price }}</p>
              </div>

              <div
                class="btn-actions pa-2 text-center"
                style="border: 1px solid green; max-width: 133px; border-radius: 15px"
              >
                <v-btn variant="text" size="x-small">
                  <v-icon
                    size="18px"
                    color="black"
                    @click="
                      function decrementCount() {
                        if (n.count > 1) {
                          {
                            {
                              n.count--
                            }
                          }
                        }
                      }
                    "
                    >mdi-minus</v-icon
                  >
                </v-btn>

                <span class="border" style="padding: 9px 12px; border-top: none">{{
                  n.count
                }}</span>
                <v-btn variant="text" size="x-small" @click="n.count++">
                  <v-icon size="18px" color="black">mdi-plus</v-icon>
                </v-btn>
              </div>
              <div class="d-flex justify-end my-2">
                <v-btn color="error" size="x-small" variant="text">Remove</v-btn>
                <v-btn color="success" size="x-small" variant="text"> Move to wishlist</v-btn>
              </div>
            </div>
          </div>
        </div>
      </v-card>
    </v-overlay>
  </div>
</template>
<style>
@media (max-width: 600px) {
  .fixed-card {
    width: 100vw !important;
    left: 0 !important;
  }
}
</style>
