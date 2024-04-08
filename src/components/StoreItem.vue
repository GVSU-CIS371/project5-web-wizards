<template>
  <v-card v-for="product in products" :key="product.id">
    <v-img :src="product.data.image" height="200px"></v-img>
    <v-card-title>{{ product.data.name }}</v-card-title>
    <v-card-subtitle>{{ product.data.category }}</v-card-subtitle>
    <v-card-text>{{ product.data.description }}</v-card-text>
    <v-card-actions style="display: flexbox;">
      <v-btn>Price: ${{ product.data.price }}</v-btn>
      <v-btn>Rating: {{ product.data.rating }}</v-btn>
      <v-btn>Stock: {{ product.data.stock }}</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useProductStore } from '../stores/ProductStore';

export default defineComponent({
  setup() {
    const productStore = useProductStore();

    return {
      products: productStore.products,
    };
  },
});
</script>
