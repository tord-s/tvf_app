<template>
    <div v-if="hasSelectedTemplate">
        <p>Populate dataset:</p>
            <transition-group name="fade" mode="out-in" tag="span">
            <div v-bind:key="data" v-for="data in template" class="container">
                <Data :data="data" class="data" />
            </div>
            </transition-group>
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
    text-align: left;
    display: flex;
    margin-left: 20vw;
    width: 60vw;
    background: #444;
}

.data {
    padding: 10px;
    width: 100%;
    border: 1px white solid;
}

button {
    margin: 4vh;
}

/* .fade-enter-active, .fade-leave-active {
  transition: all .2s;
}
.fade-enter, .fade-leave-to{
  opacity: 0;
}
.fade-enter-active {
  transition-delay: .2s;
} */

/* router transitions  */
.fade-enter-from {
  opacity: 0;
  transform: translateX(100px);
}

.fade-enter-active {
  transition: all 0.3s ease-out;
}

.fade-leave-to {
  opacity: 0;
  transform: translate(-100px);
}

.fade-leave-active {
  transition: all 0.3s ease-in;
}
</style>