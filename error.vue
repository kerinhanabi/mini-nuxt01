<template>
    <div class="mt-7 max-w-sm mx-auto text-center card">
        <p class="mt-7 text-7xl font-bold"> {{ error.statusCode }} </p>
        <p class="mt-7 text-6xl">Oops.</p>
        <p class="mt-7">{{ error.message }}</p>

        <!-- option 1: directly without any script to command button onClick redirect to home page-->
        <button class="btn my-7" @click="$router.push('/') ">Back to Home</button>

        <!-- or option 2 : pair with script to create the handle clear error function -->
        <button class="btn my-7" @click="handleClearError(error)">Back to Home</button>
    </div>
</template>

<script setup>
    defineProps(['error'])

    const handleClearError = () => clearError({ redirect: '/' })
</script>

<style scoped>

</style>