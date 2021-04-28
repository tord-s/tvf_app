<template>
    <label for="datasets">Specify dataset template:</label> 
    <select name="datasets" id="datasets" :v-bind="dataset_template" @change="updateDataset($event)" v-model="dataset_template">
        <option :key="dataset" v-for="dataset in datasets" :value="dataset.name">{{dataset.name}}</option>
    </select>
    <!-- <button @click="getTemplate">Load template</button> -->
</template>

<script>
export default {
    name: 'SpecifyTemplate',
    data() {
        return {
            dataset_template: String,
            datasets: Array
        }
    },
    async created() {
        const res = await fetch('http://localhost:5000/datasets')
        const data = await res.json()
        this.datasets = data
    },
    methods: {
        async getTemplate() {
            const dataset =  this.dataset_template
            const res = await fetch('http://localhost:5000/'+ dataset)
            const data = await res.json()
            this.$emit('update-template', data)
        },
        updateDataset(event) {
            this.dataset_template = event.target.value
            this.getTemplate() 
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
    select {
        color: #c8fc9c;
        background: black;
        padding: 10px;
        margin: 10px;
        border: 1px solid white;
        border-radius: 20px;
    }

    select:focus, select:active {
        outline: none;
    }
</style>