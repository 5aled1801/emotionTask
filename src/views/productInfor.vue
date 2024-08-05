<script>
export default {
  data() {
    return {
      prod: {
        id: 1,
        name: 'Spinneys Black Eyed peas, 500Gm',
        price: 14.25,
        img: 'https://mcprod.spinneys-egypt.com/media/catalog/product/cache/36b410f085b47d6b5accd0d7fc6177ea/3/5/356385.jpg?format=webp',
        count: 1
      }
    }
  }
}
</script>
<template>
  <div class="app">
    <v-container fluid class="top-0 position-absolute left-0 d-flex align-center">
      <div><img :src="prod.img" alt="" style="width: 40vw" /></div>
      <div>
        <h1 style="color: green">{{ prod.name }}</h1>
        <div class="my-4">
          <span class="font-weight-medium mb-4">cold Cuts </span>
          <hr style="width: 15%" />
        </div>
        <h2 class="my-6" style="color: green">EGP{{ prod.price }}</h2>
        <p class="text-h6" style="font-weight: 700">Grocery Weight</p>
        <v-select
          variant="outlined"
          style="text-align-last: center"
          width="120"
          value="750 gm"
          :items="['500 gm', '1000 gm', '1500 gm']"
        ></v-select>
        <p class="my-2">Quantity</p>
        <div class="d-flex ga-2">
          <div
            class="btn-actions pa-2 text-center"
            style="border: 1px solid green; max-width: 190px; border-radius: 15px"
          >
            <v-btn variant="text" size="x-small">
              <v-icon
                size="18px"
                color="black"
                @click="
                  function decrementCount() {
                    if (prod.count > 1) {
                      {
                        {
                          prod.count--
                        }
                      }
                    }
                  }
                "
                >mdi-minus</v-icon
              >
            </v-btn>

            <span class="border" style="padding: 9px 24px; border-top: none">{{ prod.count }}</span>
            <v-btn variant="text" size="x-small" @click="prod.count++">
              <v-icon size="18px" color="black">mdi-plus</v-icon>
            </v-btn>
          </div>
          <v-btn
            class="position-relative text-white h-auto"
            size="small"
            style="
              width: 40%;
              background: linear-gradient(45deg, #0a6c4b, #8cb114);
              border-radius: 15px;
            "
            density="comfortable"
            @click="prod.count++"
          >
            Add to cart
            <v-badge
              content="1"
              color="rgb(251 206 0) "
              style="position: absolute; right: 1%; top: 0"
            ></v-badge>
          </v-btn>
        </div>
        <p class="mt-8">
          <v-icon>mdi-clock-outline</v-icon>
          <span style="font-weight: 700">Delivered Within :</span>The Same Day
        </p>
        <hr class="my-4" />
        <div class="d-flex">
          <img src="../assets/logo.svg" width="20" alt="" />
          <p>Sold and delivered by Spinneys</p>
        </div>
        <hr class="my-4" />
      </div>
    </v-container>
  </div>
</template>
<style>
.v-field__field {
  height: 40px;
}
.v-field__input {
  padding: 7px;
}
@media (max-width: 600px) {
  .v-container {
    flex-direction: column !important;
  }
  img {
    width: 90vw !important;
  }
}
</style>
