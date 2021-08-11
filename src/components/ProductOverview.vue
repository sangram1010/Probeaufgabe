<template>
  <div class="product-overview">
    <div class="bar">AppTitle</div>
    <div class="filters">
      <label class="label" @click="changeTab('all')">All</label>
      <label class="label" @click="changeTab('available')">Available</label>
      <label class="label" @click="changeTab('watch')">Watch List</label>
    </div>
    <div class="title">
      <h1>Products</h1>
      <h1>Subtitle</h1>
    </div>

    <div class="grid" v-if="tab === 'all'">
      <ProductTile
        v-for="product in products"
        :key="product.id"
        :name="product.name"
        :imageURL="product.imageURL"
        :available="product.available"
        :description="product.description"
        :price="product.price"
        :tab="tab"
      />
    </div>
    <div class="grid" v-if="tab === 'available'">
      <ProductTile
        v-for="product in products"
        :key="product.id"
        :name="product.name"
        :imageURL="product.imageURL"
        :available="product.available"
        :description="product.description"
        :price="product.price"
        :tab="tab"
      />
    </div>
    <div class="grid" v-if="tab === 'watch'">
      <ProductTile
        v-for="product in products"
        :key="product.id"
        :name="product.name"
        :imageURL="product.imageURL"
        :available="product.available"
        :description="product.description"
        :price="product.price"
        :tab="tab"
      />
    </div>
  </div>
</template>
<script>
import axios from "axios";
import ProductTile from "./ProductTile.vue";
export default {
  name: "ProductOverview",
  components: { ProductTile },
  data() {
    return {
      products: null,
      availableProduct: null,
      watchList: null,
      tab: "all",
    };
  },
  methods: {
    getProducts() {
      axios
        .get(
          `https://gist.githubusercontent.com/benfranke/
c33280a8df5f4f9db2e63ad45cab26a4/raw/
f3ad6c00ff520c2667305103d5705bcbb57a7778/products.json`
        )
        .then(
          (response) => (
            (this.products = response.data.products),
            console.log(response.data.products[0].name)
          )
        );
    },
    changeTab(tab) {
      this.tab = tab;
      console.log(this.tab);
    },
  },
  mounted() {
    this.getProducts();
  },
};
</script>
<style>
.bar {
  background-color: cornflowerblue;
  color: white;
  text-align: center;
  width: 100%;
  padding: 6px;
}
.filters {
  background-color: lightgrey;
  padding: 10px;
  text-align: center;
}
.label {
  padding: 10px;
  margin: 30px;
  cursor: pointer;
}
.title {
  padding: 12px;
}
</style>
