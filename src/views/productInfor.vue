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
        <p style="text-decoration: underline">code Cuts</p>
        <h2 style="color: green">EGP{{ prod.price }}</h2>
        <p style="font-weight: 700">Grocery Weight</p>
        <select
          name="weight"
          id="weight"
          style="border: 1px solid gray; border-radius: 5px; text-align: center"
        >
          <option value="750gm">750gm</option>
          <option value="500gm">500gm</option>
          <option value="1500gm">1500gm</option></select
        ><Br />
        <p class="my-2">Quantity</p>
        <div class="d-flex ga-2">
          <div
            class="btn-actions"
            style="
              border: 1px solid green;
              text-align: center;
              max-width: 190px;
              border-radius: 15px;
            "
          >
            <v-btn variant="text" size="x-small">
              <v-icon size="18px" color="green" @click="prod.count++">mdi-plus</v-icon>
            </v-btn>
            <span class="border" style="padding: 2px 24px; border-top: none">{{ prod.count }}</span>
            <v-btn variant="text" size="x-small">
              <v-icon
                size="18px"
                color="green"
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
          </div>
          <button
            style="
              position: relative;
              width: 50%;
              border: 1px solid rgb(3, 113, 77);
              border-radius: 14px;
              color: white;
              width: 50%;
              background: linear-gradient(45deg, #0a6c4b, #8cb114);
              border-radius: 15px;
            "
            @click="prod.count++"
          >
            Add Item
            <v-badge color="warning" content="1" style="position: absolute; right: 1%"></v-badge>
          </button>
        </div>
        <p class="mt-8">
          <v-icon>mdi-clock</v-icon> <span style="font-weight: 700">Delivered Within :</span>The
          Same Day
        </p>
        <hr class="my-2" />
        <p>Sold and delivered by Spinneys</p>
      </div>
    </v-container>
  </div>
</template>
<style>
@media (max-width: 600px) {
  .v-container {
    flex-direction: column !important;
  }
  img {
    width: 90vw !important;
  }
}
</style>
