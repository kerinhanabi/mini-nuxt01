<template>
    <div>
        <h2>About</h2>
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloribus odio amet hic sunt quis quisquam possimus nostrum, distinctio mollitia esse.</p>
        
        <div>{{ data }}</div> <!-- getting msg from self custom api -->
    </div>
</template>

<script setup>
    //way #1 to get data from self custom api 
    const { data } = await useFetch('/api/mini_api')
    
</script>

<style scoped>

</style>