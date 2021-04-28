<template>
  <Header/>
   <router-view v-slot="{ Component }">
    <transition name="route" mode="out-in">
      <component :is="Component"></component>
    </transition>
  </router-view>
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
  text-decoration: none;
}

html, body {
  margin: 0px;
  padding: 0px;
}

input {
  color: #c8fc9c;
  background: black;
  border: 1px #c8fc9c solid;
  text-align: left;
}

button {
  background: #c8fc9c;
  color: black;
  padding: 10px;
  border-radius: 20px;
}

a:hover,
a.router-link-active {
  border-bottom: #c8fc9c solid 2px;
}


/* router transitions  */
.route-enter-from {
  opacity: 0;
}

.route-enter-active {
  transition: all 0.3s ease;
}

.route-leave-to {
  opacity: 0;
}

.route-leave-active {
  transition: all 0.3s ease-in;
}
</style>
