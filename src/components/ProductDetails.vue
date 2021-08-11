<template>
  <div class="product-tile">
    <img class="img" :src="imageURL" />
    <div class="details">
      <h1>Name: {{ name }}</h1>

      <h1>Price: {{ price.value }} {{ price.currency }}</h1>
    </div>
    <div>
      <h1>Description: {{ description }}</h1>
    </div>
    <button>Vormerken</button>
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
