<template>
  <div class="card" style="width: 18rem;">
    <img :src="product.image" :alt="product.title" class="card-img-top">
    <h5 class="card-title">{{ product.title }}</h5>
    <p class="card-price"> $ {{ product.price.toFixed(2) }}</p>

    <!-- Botões -->
    <button class="btn btn-primary" @click="openModal">Comprar</button>
    <NuxtLink class="btn btn-terciary" to="/cart">Carrinho</NuxtLink>

    <!-- Modal -->
    <div class="modal fade" tabindex="-1" ref="modalRef">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title">Confirmar Compra</h5>
            <button type="button" class="btn-close" @click="closeModal"></button>
          </div>
          <div class="modal-body">
            <p>Deseja realmente comprar <strong>{{ product.title }}</strong> por ${{ product.price.toFixed(2) }}?</p>
          </div>
          <div class="modal-footer">
            <button class="btn btn-secondary" @click="closeModal">Cancelar</button>
            <button class="btn btn-primary" @click="confirmPurchase">Confirmar</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import bootstrap from 'bootstrap/dist/js/bootstrap.bundle.min.js'


const props = defineProps({
  product: { type: Object, required: true }
})

const modalRef = ref(null)
let bootstrapModal = null

onMounted(() => {
  // Inicializa o modal do Bootstrap
  bootstrapModal = new bootstrap.Modal(modalRef.value)
})

const openModal = () => bootstrapModal.show()
const closeModal = () => bootstrapModal.hide()
const confirmPurchase = () => {
  console.log('Produto comprado:', props.product)
  bootstrapModal.hide()
}
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