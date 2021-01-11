<template>
  <div>
    <h2>Welcome to the best dad jokes</h2>
    <img src="../static/smile.png" alt="" width="40%">
  </div>
</template>

<script>
export default {
  head() {
        return {
            title: 'Welcome to Dad Jokes',
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
