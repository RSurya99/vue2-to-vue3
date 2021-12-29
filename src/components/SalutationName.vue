<template>
  <div>
    <select @change="$emit('update:salutation', $event.target.value)">
      <option value="">-</option>
      <option
        v-for="item of salutations"
        :key="item"
        :selected="salutation === item"
        :value="item"
      >
        {{ item }}
      </option>
    </select>

    <input
      @input="$emit('update:name', $event.target.value)"
      type="text"
      :value="name"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      salutations: ['Ms.', 'Mrs.', 'Miss', 'Mr.', 'Dr.', 'Sir.'],
    }
  },
  props: {
    salutation: {
      type: String,
      default: '',
    },
    name: {
      type: String,
      default: '',
    },
  },
}
</script>
