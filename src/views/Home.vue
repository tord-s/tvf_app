<template>
  <div class="home">
    <AddDataset />
  </div>
</template>

<script>
// @ is an alias to /src
import AddDataset from '../components/AddDataset'

export default {
  name: 'Home',
  components: {
    AddDataset
  }
}
</script>

<style scoped>
.home{
  min-height: 80vh;
}
</style>
