<template>
  <div>
    <button @click="onClick">
        {{ text }}
    </button>
  </div>
</template>

<script>
export default {
  name: 'AppButton',
  props: {
    text: String,
    onClick: {
      type: Function,
      required: false
    }
  }
}
</script>

<style scoped>
</style>
