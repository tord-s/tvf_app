<template>
    <div>{{data.symbol}}</div>
    <input type="text" v-model="data.values">
    <div>{{data.unit}}</div>
    <div>{{data.data_type}}</div>
</template>

<script>
export default {
    name: 'Data',
    props: {
        data: Object,
    },
    data() {
        return {
            symbol: String,
            values: Array,
            unit: String,
            data_type: String,
        }
    }
}
</script>

<style scoped>
div {
        padding: 10px;
        overflow: hidden;
        white-space: nowrap;
        max-width: 50vw;
        border: 1px #c8fc9c solid;
}
</style>