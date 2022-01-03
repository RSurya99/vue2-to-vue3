<template>
  <div>
    <select @change="updateSalutation">
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

    <input @input="updateName" type="text" :value="name" />
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
    salutationModifiers: {
      default: () => ({}),
    },
    name: {
      type: String,
      default: '',
    },
    nameModifiers: {
      default: () => ({}),
    },
  },
  setup(props, { emit }) {
    const updateSalutation = (event) => {
      let val = event.target.value
      if (props.salutationModifiers.capitalize) {
        val = val.toUpperCase()
      }

      emit('update:salutation', val)
    }

    const updateName = (event) => {
      let val = event.target.value
      if (props.nameModifiers.reverse) {
        val = val.split('').reverse().join('')
      }
      if (props.nameModifiers.capitalize) {
        val = val.charAt(0).toUpperCase() + val.slice(1)
      }

      emit('update:name', val)
    }

    return {
      updateSalutation,
      updateName,
    }
  },
}
</script>
