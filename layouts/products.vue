<template>
    <div>
        <!-- custom navbar for products related pages  -->
        <header class="shadow-sm bg-white">
            <nav class="container mx-auto p-4">
                <NuxtLink to="/products" class="font-bold">Mini Nuxt 01 : goto Products index</NuxtLink>
                <!-- p>// Header ends here</p -->
            </nav>
        </header>

        <!-- Output Page Content here -->
         <div class="container mx-auto p-4">
            <slot />
        </div>

        <footer class="container mx-auto p-4 flex justify-between border-t-2">
            <!--p>// Footer starts here</p -->
            <ul class="flex gap-4">
                <li><NuxtLink to="/">Home</NuxtLink></li>
                <li><NuxtLink to="/about">About</NuxtLink></li>
                <li><NuxtLink to="/products">Products</NuxtLink></li>
            </ul>
        </footer>
    </div>
</template>

<script setup>

</script>

<style scoped> 
    .router-link-exact-active{
        color: #12b488;
    }
</style>