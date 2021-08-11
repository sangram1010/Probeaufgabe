<template>
  <div class="product-tile" v-if="tab === 'all'">
    <img class="img" :src="imageURL" />
    <div class="details">
      <h1>Name: {{ name }}</h1>
      <h1>Description: {{ description }}</h1>
      <h1>Price: {{ price.value }} {{ price.currency }}</h1>
    </div>
  </div>
  <div class="product-tile" v-if="tab === 'available' && available === true">
    <img class="img" :src="imageURL" />
    <div class="details">
      <h1>Name: {{ name }}</h1>
      <h1>Description: {{ description }}</h1>
      <h1>Price: {{ price.value }} {{ price.currency }}</h1>
    </div>
  </div>
  <div class="product-tile" v-if="tab === 'watch'">
    <img class="img" :src="imageURL" />
    <div class="details">
      <h1>Name: {{ name }}</h1>
      <h1>Description: {{ description }}</h1>
      <h1>Price: {{ price.value }} {{ price.currency }}</h1>
    </div>
  </div>
</template>
<script>
//import axios from "axios";

export default {
  name: "ProductTile",
  props: {
    name: {
      type: String,
      required: true,
    },
    imageURL: {
      type: String,
      required: true,
    },
    available: {
      type: Boolean,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    price: {
      type: Object,
      required: true,
    },
    tab: {
      type: String,
      required: true,
    },
  },

  /* mounted() {
    axios
      .get(
        `https://gist.githubusercontent.com/benfranke/
c33280a8df5f4f9db2e63ad45cab26a4/raw/
f3ad6c00ff520c2667305103d5705bcbb57a7778/products.json`
      )
      .then((response) => (this.products = response))
      .then(console.log(this.products));
  },*/
};
</script>
<style>
.product-tile {
  display: grid;
  grid-template-columns: 1fr 3fr;
  width: 100%;
  border: 1px solid black;
}
.details {
  padding: 10px;
}
.label {
  padding: 10px;
  margin: 30px;
}
.title {
  padding: 12px;
}
.img {
  padding: 12px;
}
</style>
