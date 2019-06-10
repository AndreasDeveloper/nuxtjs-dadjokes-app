<template>
    <div>
        <h1>About DadJokes</h1>
        <p>This is an app that displays dad jokes fetched from API</p>
    </div>
</template>

<script>
export default {
    // Head Tag
    head() {
        return {
            title: 'About The App',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Best place for dad jokes'
                }
            ]
        }
    }
};
</script>

<style scoped>

</style>
