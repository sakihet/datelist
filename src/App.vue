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
        @update="prefixValue = $event"
      />
      <InputLabeled
        inputId="startDate"
        inputType="date"
        labelName="start date"
        :value="startDateValue"
        @update="startDateValue = $event"
      />
      <InputLabeled
        inputId="days"
        inputType="number"
        labelName="days"
        :value="daysValue"
        @update="daysValue = $event"
      />
      <InputLabeled
        inputId="format"
        inputType="text"
        labelName="format"
        :value="formatValue"
        @update="formatValue = $event"
      />
      <AppTextarea
        :readonly="true"
        rows="10"
        :value="generatedString"
      />
      <AppButton
        text="copy to clipboard"
        @onClick="copy"
      />
      <a href="https://github.com/sakihet/datelist" target="_blank">github</a>
      <p>version: {{ version }}</p>
    </div>
  </div>
</template>

<script>
import AppButton from './components/AppButton'
import AppHeader from './components/AppHeader'
import AppTextarea from './components/AppTextarea'
import InputLabeled from './components/InputLabeled'
import dayjs from 'dayjs'
import mcopy from 'modern-copy'
import { version } from '../package.json'

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
      startDateValue: '',
      daysValue: 7,
      formatValue: 'YYMMDDddd',
      version: version
    }
  },
  created: function () {
    this.startDateValue = dayjs().format('YYYY-MM-DD')
  },
  computed: {
    generatedString: function () {
      let str = ''
      for (var i = 0; i < this.daysValue; i++) {
        str += this.prefixValue + dayjs(this.startDateValue).add(i, 'day').format(this.formatValue)
        str += '\n'
      }
      return str
    }
  },
  methods: {
    copy: function () {
      mcopy(this.generatedString)
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
