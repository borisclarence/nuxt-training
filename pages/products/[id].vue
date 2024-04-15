<template>
    <div>
        <!-- head meta de test -->
        <!-- <head>
            <Title>Nuxt training | {{ product.title }}</Title>
            <Meta name="description" :content="product.description" />
        </head> -->

        <ProductDetail :product="product" />
    </div>
</template>

<script setup>
    const { id } = useRoute().params
    const uri = 'https://fakestoreapi.com/products/' + id

    // fetch one product
    const { data: product } = await useFetch(uri, { key: id });

    if (!product.value) {
        throw createError({ statusCode: 404, statusMessage: 'Product not found', fatal: true })
    }

    definePageMeta({
        layout: 'products'
    })
</script>

<style lang="scss" scoped>

</style>