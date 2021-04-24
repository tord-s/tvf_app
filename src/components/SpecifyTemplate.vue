<template>
    <p>Specify dataset:</p>
    Lorem:<input type="text" value="Lorem"><br>
    Ipsum:<input type="text" value="Ipsum"><br>
    Lorem:<input type="text" value="Lorem"><br>
    Ipsum:<input type="text" value="Ipsum"><br>
    <button @click="getTemplate">Load template</button>
</template>

<script>
export default {
    name: 'SpecifyTemplate',
    methods: {
        async getTemplate() {
            const res = await fetch('http://localhost:5000/only_data_example_ship')
            const data = await res.json()
            this.$emit('update-template', data)
        }
    }
}
</script>

<style scoped>
    input {
        padding: 5px;
        margin: 2px;
    }
    button {
        margin-top: 20px;
    }

</style>