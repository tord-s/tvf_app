<template>
    <h1>Add dataset</h1>
    <SpecifyTemplate @update-template="updateTemplate" />
    <PopulateDataset @data-submitted="dataSubmitted" :template=template :hasSelectedTemplate="hasSelectedTemplate" />
</template>

<script>
import SpecifyTemplate from '@/components/SpecifyTemplate'
import PopulateDataset from '@/components/PopulateDataset'
import router from '../router'

export default {
    name: 'AddDataset',
    data() {
        return {
            template: [],
            hasSelectedTemplate: false,
        }
    },
    components: {
        SpecifyTemplate,
        PopulateDataset,
    },
    methods: {
        updateTemplate(template) {
            this.hasSelectedTemplate = true
            this.template = template
        },
        dataSubmitted() {
            router.push('recipt')
        }
    }
}
</script>

<style scoped>
h1 {
    padding-top: 2vh;
}
* {
    margin: 0px;
}
</style>
