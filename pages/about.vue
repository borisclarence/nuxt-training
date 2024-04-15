<template>
    <div>
        <h2>about</h2>

        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Vero, saepe?</p>
        <p>Lorem ipsum dolor sit amet consectetur, consectetur adipisicing elit. Id laboriosam nihil,
            maxime enim molestiae ad?.</p>
        <div>{{ data }}</div>
    </div>
</template>

<script setup>
    const { data } = await useFetch('/api/trainer?name=mario', {
        method: 'post',
        body: { age: 30 }
    })

    //when we cell external api => const { data } = await useFetch('/api/trainer')

    //when we cell external api with currencyKey => const { data } = await useFetch('/api/currency/GBP')
</script>

<style lang="scss" scoped>
    h2 {
        margin-bottom: 20px;
        font-size: 36px;
    }

    p {
        margin: 0 20px;
    }
</style>