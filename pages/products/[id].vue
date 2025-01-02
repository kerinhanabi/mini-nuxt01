<template>
    <div>
        <!-- way #2 : custom overwrite title and meta tag in head with built in nuxt features -->
        <Head>
            <Title>Mini Nuxt 01 | {{ product.title }}</Title>
            <Meta name="description" :content="product.description" />
        </Head>

        <!-- h2>Product details for {{ id }}</h2>
        <h3>Product ID: {{ $route.params.id }}</h3>
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus odio amet hic sunt quis quisquam possimus nostrum, distinctio mollitia esse.</p -->
        <ProductDetails :product="product"/>
    </div>
</template>

<script setup>
    const { id } = useRoute().params
    const route = useRoute().params.id
    const uri = 'https://fakestoreapi.com/products/' + id

    //fetch the selected product data
    const { data: product } = await useFetch(uri, { key: id })

    if (!product.value) {
        throw createError({
            statusCode: 404,
            statusMessage: 'Product not found',
            fatal: true
        })
    }

    //script to command nuxt use this custom layout/products for products related pages with <slot/> tag
    definePageMeta({
        layout: 'products'
    })
</script>

<style scoped>

</style>