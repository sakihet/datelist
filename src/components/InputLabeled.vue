<template>
  <div class="input-labeled">
    <label
      class="cell left"
      :for="inputId"
    >
      {{ labelName }}
    </label>
    <div class="cell right">
      <AppInput
        :inputId="inputId"
        :inputType="inputType"
        :value="value"
        @update="$emit('update', $event)"
      />
    </div>
  </div>
</template>

<script>
import AppInput from './AppInput'

export default {
  name: 'InputLabeled',
  components: {
    AppInput
  },
  props: {
    inputType: {
      type: String,
      required: true
    },
    inputId: {
      type: String,
      required: true
    },
    labelName: {
      type: String
    },
    value: [String, Number, Boolean]
  }
}
</script>

<style scoped>
.input-labeled {
  display: flex;
}
.cell {
  flex: 1;
}
.left {
  text-align: right;
}
.right {
  text-align: left;
}
</style>
