<template>
  <SalutationName
    v-model:salutation="form.salutation"
    v-model:name="form.name"
  />
  <pre>{{ form }}</pre>
</template>

<script>
import SalutationName from '@/components/SalutationName.vue'
import { reactive } from 'vue'

export default {
  name: 'App',
  components: {
    SalutationName,
  },
  setup() {
    const form = reactive({
      salutation: '',
      name: '',
    })
    return {
      form,
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
