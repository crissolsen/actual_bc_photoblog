<template>
    <nav>
        <nuxt-link :to="`/`"><h1>B | C</h1></nuxt-link>
        <h2>Photography Blog</h2>
    </nav>
</template>

<style scoped>
    nav {
        justify-self: center;
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
        width: 100%;
    }

    h1 {
        font-size: 10vmax;
        text-align: center;
    }

    h2 {
        font-size: 2em;
    }
    
</style>