<template>
    <div>
        <h1>About DadJokes</h1>
        <p>This is an app that displays dad jokes</p>
        <p>Created to learn <a href="https://nuxtjs.org/" target="_blank" rel="noopener noreferrer">Nuxt.js</a></p>
        <p>Created by referencing <a href="https://www.youtube.com/c/TraversyMedia">Traversy Media's</a> <b><a href="https://youtu.be/ltzlhAxJr74" target="_blank">Nuxt JS Crash Course</a></b></p>
    </div>
</template>

<script>
export default {
    head() {
        return {
            title: 'About us',
            meta: [
                {
                    hid: "description",
                    name: "description",
                    content: "Best place for dad jokes"
                }
            ]
        }
    }
}
</script>

<style>

</style>