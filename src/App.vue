<template>
  <div id="app">
    <main>
      <ListVue></ListVue>
    </main>
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