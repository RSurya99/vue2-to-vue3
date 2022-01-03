<template>
  <label>{{ label }}</label>
  <input
    v-bind="{
      ...$attrs,
      onInput: (event) => {
        $emit('update:modelValue', event.target.value)
      },
    }"
    :value="modelValue"
  />
</template>

<script>
export default {
  // inheritAttrs: false,
  // emits: {}, // set emit desc
  props: {
    modelValue: {
      type: [String, Number],
      default: '',
    },
    label: {
      type: String,
      default: null,
    },
  },
}
</script>

<style lang="scss" scoped></style>
