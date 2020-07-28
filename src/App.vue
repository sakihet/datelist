<template>
  <div id="app">
    <div class="container">
      <AppHeader
        text="Datelist"
      />
      <InputLabeled
        inputId="prefix"
        inputType="text"
        labelName="prefix"
        :value="prefixValue"
        @input="prefixValue = $event"
      />
      <InputLabeled
        inputId="locale"
        inputType="text"
        labelName="locale"
        :value="localeValue"
        @input="localeValue = $event"
      />
      <InputLabeled
        inputId="startDate"
        inputType="date"
        labelName="start date"
        :value="startDateValue"
        @input="startDateValue = $event"
      />
      <InputLabeled
        inputId="days"
        inputType="number"
        labelName="days"
        :value="daysValue"
        @input="daysValue = $event"
      />
      <InputLabeled
        inputId="format"
        inputType="text"
        labelName="format"
        :value="formatValue"
        @input="formatValue = $event"
      />
      <AppTextarea />
      <AppButton
        text="copy to clipboard"
      />
    </div>
  </div>
</template>

<script>
import AppButton from './components/AppButton'
import AppHeader from './components/AppHeader'
import AppTextarea from './components/AppTextarea'
import InputLabeled from './components/InputLabeled'

export default {
  name: 'App',
  components: {
    AppButton,
    AppHeader,
    AppTextarea,
    InputLabeled
  },
  data () {
    return {
      prefixValue: '# ',
      localeValue: 'en',
      startDateValue: '',
      daysValue: 7,
      formatValue: 'YYMMDDddd'
    }
  },
  methods: {
    copy: function () {
      console.log('copy')
    }
  }
}
</script>

<style>
body {
  margin: 0;
}
#app {
  text-align: center;
}
.container {
  display: flex;
  flex-direction: column;
}
</style>
