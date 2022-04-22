<template>
    <div class="page-search">
        <div class="columns is-multiline">
            <div class="column is-12">
                <h1 class="title">Adicione um produto</h1>

                <h3 class="is-size-5">Nome:</h3>
                <input type="text" class="input" placeholder="Nome" name="productName" v-model="product.name">
                <h3 class="is-size-5">Slug:</h3>
                <input type="text" class="input" placeholder="Slug" name="productSlug" v-model="product.slug">
                <h3 class="is-size-5">Categoria:</h3>
                <input type="text" class="input" placeholder="Categoria(Monitor ou Celular)" name="productCategory" v-model="product.category">
                <h3 class="is-size-5">Descrição:</h3>
                <input type="text" class="input" placeholder="Descrição" name="productDescription" v-model="product.description">
                <h3 class="is-size-5">Preço:</h3>
                <input type="number" class="input" placeholder="Preço" name="productPrice" v-model="product.price">
                <button class="button is-success" style="margin-top: 15px" @click="addProduct()">Adicionar Produto</button>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
import ProductBox from '@/components/ProductBox'

export default {
    name: 'Search',
    components: {
        ProductBox
    },
    data(){
        return {
            product: {
                name: '',
                slug: '',
                category: '',
                description: '',
                price: 0
            }
        }
    },
    mounted() {
        document.title = 'Adicione | Loja Virtual'
    },
    methods: {
        async addProduct(){

            this.$store.commit('setIsLoading', true)
            await axios
                .post('/api/v1/products/', this.product)
                .then(response => {
               
                })
                .catch(error => {
                console.log(error)
                })

            this.$store.commit('setIsLoading', false)
        }
    }
}
</script>