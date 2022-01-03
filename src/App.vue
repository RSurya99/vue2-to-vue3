<template>
  <SalutationName
    v-model:salutation.capitalize="form.salutation"
    v-model:name.capitalize.reverse="form.name"
  />
  <pre>{{ form }}</pre>

  <BaseInput
    v-model="email"
    label="Email: "
    type="email"
    class="test-class"
    @blur="email = 'test@test.cold'"
  />
</template>

<script>
import SalutationName from '@/components/SalutationName.vue'
import BaseInput from '@/components/BaseInput.vue'
import { reactive, ref } from 'vue'

export default {
  name: 'App',
  components: {
    SalutationName,
    BaseInput,
  },
  setup() {
    const email = ref('')
    const form = reactive({
      salutation: '',
      name: '',
    })
    return {
      form,
      email,
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
