<template>
    <div v-if="hasSelectedTemplate">
        <p>Populate dataset:</p>
        <div v-bind:key="data" v-for="data in template" class="container">
            <Data :data="data" />
        </div>
        <button value="Submit to Platform" @click="$emit('data-submitted')" > Save to Platform</button>
    </div>
</template>

<script>
import Data from '@/components/Data'

export default {
    name: 'PopulateDataset',
    props: {
        template: Array,
        hasSelectedTemplate: Boolean
    },
    components: {
        Data
    },
}
</script>

<style scoped>
.container {
    display: grid;
    grid-template-columns: [name] 40vw [value] 10vw [unit] 10vw [data_type] 10vw;
    padding-left: 10vw;
    overflow: hidden;
    grid-column-gap: 30px;
    grid-row-gap: 30px;
}
button {
    margin: 4vh;
}
</style>