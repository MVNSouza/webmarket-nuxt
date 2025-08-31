<template>
    <div>
        <NavBar class="navbar fixed-top" />
        <main>
            <h2>Lista de Produtos</h2>
            <div v-if="pending">Carregando os produtos...</div>
            <div v-if="error">Erro ao carregar os produtos :/ </div>
            <div v-else class="row g-10 text-center">
                    <CardProduto
                    v-for="produto in products"
                    :key="produto.id"
                    :product="produto"
                    ></CardProduto>
            </div>

        </main>
        <Footer />
    </div>
</template>

<script setup>
 const { data: products, pending, error } = await useFetch('https://fakestoreapi.com/products')
</script>

<style scoped>

    main {
        height: 100%;
        width: 100%;
        padding: 2rem;
        align-items: center;
        padding-top: 75px;
    }
    
</style>