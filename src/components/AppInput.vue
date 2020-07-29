<template>
  <div>
    <input
      :id="inputId"
      :type="inputType"
      :value="value"
      @input="$emit('update', $event.target.value)"
    >
  </div>
</template>

<script>
export default {
  name: 'AppInput',
  props: {
    inputId: {
      type: String,
      required: true
    },
    inputType: {
      type: String,
      required: true
    },
    value: [String, Number, Boolean]
  }
}
</script>

<style scoped>
</style>
