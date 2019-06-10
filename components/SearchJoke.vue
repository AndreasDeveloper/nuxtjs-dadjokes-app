<template>
    <form v-on:submit.prevent="onSubmit"> 
        <input type="text" v-model="text" placeholder="Search Jokes..">
        <input type="submit" value="Search">
    </form>
</template>

<script>
export default {
    name: 'SearchJoke',
    // Data
    data() {
        return {
            text: ''
        }
    },
    // Methods
    methods: {
        onSubmit() {
            this.$emit('search-text', this.text);
            this.text = '';
        }
    }
};
</script>

<style scoped>

</style>
