<template>
    <div class="container">
        <h2>Header content</h2>
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
    </div>
    
</template>

<style scoped>
.container {
    background: #444;
    margin: 0px;
    height: 10vh;
}

h2 {
    padding-top: 2vh;
}

* {
    margin: 0px
}
</style>