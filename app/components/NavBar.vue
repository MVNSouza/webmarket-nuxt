<script setup>
import { NuxtLink } from '#components';


</script>

<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary" data-bs-theme="dark">
    <div class="container-fluid">
      <NuxtLink class="navbar-brand" to="/">Web Market </NuxtLink>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
          aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <NuxtLink class="nav-link" aria-current="page" to="/">Início</NuxtLink>
            </li>
            <li class="nav-item">
              <NuxtLink class="nav-link" to="/about" >Sobre</NuxtLink>
            </li>
          
          </ul>
        </div>
        <NuxtLink class="nav-link" to="/cart" style="color:beige; font-weight: 500;">Carrinho 🛒</NuxtLink>
    </div>
  </nav>
</template>


<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
}
</style>