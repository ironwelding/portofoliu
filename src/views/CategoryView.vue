<template>
    <div class="category-container">
        <section>
            <h1>Work in progress ( {{ $route.params.id }} )</h1>
            <router-link to="/">Go back</router-link>
        </section>
    </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.category-container {
    display: grid;
    place-items: center;
    height: 100vh;

    section {
        display: flex;
        flex-direction: column;
        gap: 2em;

        h1 {
            color: #0D7E86;
            font-size: 4em;
            
        }
        
        a {
            font-size: 3em;
            border: 1px solid #ccc;
            padding: 1em;
            text-align: center;
            color: #ccc;
            text-decoration: none;
            border-radius: 5px;
        }
    }
}
</style>