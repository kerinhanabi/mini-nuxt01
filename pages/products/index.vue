<template>
    <div>
        <h2>Products</h2>
        <p>This is a products page.</p>
        <div class="grid grid-cols-4 gap-5">
            <div v-for="p in products" :key="p.id">
                <ProductCard :product="p"/>
            </div>
        </div>
    </div>
</template>

<script setup>
//script to command nuxt use this custom layout/products for products related pages with <slot/> tag
    definePageMeta({
        layout: 'products'
    })

    //fetch products' data
    const { data: products } = await useFetch('https://fakestoreapi.com/products')

    //one way to overwrite the default global title and meta tag in head
    useHead ({
        title: 'Mini Nuxt 01 | All Products',
        meta: [
            { name: 'description', content: 'List of all products' }
        ]
    })
</script>

<style scoped>

</style>