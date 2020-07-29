<template>
  <div>
    <textarea
      :readonly="readonly"
      :rows="rows"
      :value="value"
    ></textarea>
  </div>
</template>

<script>
export default {
  name: 'AppTextarea',
  props: {
    readonly: Boolean,
    rows: String,
    value: String
  }
}
</script>

<style scoped>
</style>
