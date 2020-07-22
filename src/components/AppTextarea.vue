<template>
  <div>
    <textarea
        :value="value"
      @input="$emit('input', $event.target.value)"
      @change="$emit('change', $event.target.checked)"
    ></textarea>
  </div>
</template>

<script>
export default {
  name: 'AppTextarea',
  props: {
    value: String
  }
}
</script>

<style scoped>
</style>
