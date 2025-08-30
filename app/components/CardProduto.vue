<template>
    <div class="card" style="width: 18rem;">
    <img :src="product.image" alt="Foto de {{ product.title }}" class="card-img-top">
    <h5 class="card-title">{{ product.title }}</h5>
    <!-- <p class="card-text">{{ product.description }}</p> -->
    <p class="card-price"> $ {{ product.price.toFixed(2) }}</p>
    <a href="#" class="btn btn-primary">Comprar</a>
    <NuxtLink class="btn btn-terciary" to="/cart">Carrinho</NuxtLink>
  </div>
</template>

<script setup>
import { NuxtImg } from '#components';

defineProps({
  product: {
    type: Object,
    required: true
  }
})




</script>

<style scoped>

  .card-img-top{
    height: 120px;
    width: 120px;
  }
  .card {
    padding: 1rem;
    align-items: center;
    margin: 2rem;
  }
  .card-text {
    font-size: 0.7rem;
    color: #14141450;
  }
  .card-price {
    font-weight: bold;
  }
</style>