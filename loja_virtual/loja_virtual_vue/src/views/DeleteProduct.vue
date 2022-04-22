<template>
    <div class="page-search">
        <div class="columns is-multiline">
            <div class="column is-12">
                <h1 class="title">Delete um produto</h1>
                <h3 class="is-size-5">Nome:</h3>
                <input type="text" class="input" placeholder="Nome" name="productName" v-model="product.name">
                <h3 class="is-size-5">Slug:</h3>
                <input type="text" class="input" placeholder="Slug" name="productSlug" v-model="product.slug">
                <button class="button is-danger" style="margin-top: 15px" @click="deleteProduct()">Remover Produto</button>
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
            }
        }
    },
    mounted() {
        document.title = 'Delete | Loja Virtual'
    },
    methods: {
        async deleteProduct(){

            this.$store.commit('setIsLoading', true)
            await axios
                .delete('/api/v1/products/', this.product)
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