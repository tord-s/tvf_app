<template>
    <span>
        {{data.symbol}}
        <input type="text" v-model="data.values" size="10">
        {{data.unit}}
        {{data.data_type}}
    </span>
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
    },
    methods: {
        lengthValues() {
            return this.values.length
        }
    }
}
</script>

<style scoped>
input {
        padding: 5px;
        box-sizing: content-box;
        border: 1px #c8fc9c solid;
}

</style>