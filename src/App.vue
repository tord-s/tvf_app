<template>
  <Header/>
  <router-view/>
  <Footer/>
</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer'

export default {
  components: {
    Header,
    Footer,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #c8fc9c;
  background: black;
}

a {
  color: #c8fc9c;
}

html, body {
  margin: 0px;
  padding: 0px;
}

input {
  color: #c8fc9c;
  background: black;
  border: 1px #c8fc9c solid;
  text-align: center;
}

button {
  background: #c8fc9c;
  color: black;
  padding: 10px;
  border-radius: 20px;
}
</style>
