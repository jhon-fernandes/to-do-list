<template>
  <div id="app">
    <ListVue></ListVue>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import ListVue from './components/List.vue'

export default defineComponent({
  components: 
  {
    ListVue
  }
})
</script>

<style scoped>

</style>