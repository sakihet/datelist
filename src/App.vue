<template>
  <div id="app">
    <div class="container">
      <AppHeader
        text="Datelist"
      />
      <FormCentered>
        <template v-slot:leftContent>
          <label for="prefix">prefix</label>
        </template>
        <template v-slot:rightContent>
          <AppInput
            inputType="text"
            :value="prefix"
            @input="prefix = $event"
          />
        </template>
      </FormCentered>
      <FormCentered>
        <template v-slot:leftContent>
          <label for="locale">locale</label>
        </template>
        <template v-slot:rightContent>
          <AppInput
            inputType="text"
            :value="locale"
            @input="locale = $event"
          />
        </template>
      </FormCentered>
      <FormCentered>
        <template v-slot:leftContent>
          <label for="text">start date</label>
        </template>
        <template v-slot:rightContent>
          <AppInput
            inputType="date"
            :value="startDate"
            @input="startDate = $event"
          />
        </template>
      </FormCentered>
      <FormCentered>
        <template v-slot:leftContent>
          <label for="days">days</label>
        </template>
        <template v-slot:rightContent>
          <AppInput
            inputType="number"
            :value="days"
            @input="days = $event"
          />
        </template>
      </FormCentered>
      <FormCentered>
        <template v-slot:leftContent>
          <label for="format">format</label>
        </template>
        <template v-slot:rightContent>
          <AppInput
            inputType="text"
            :value="format"
            @input="format = $event"
          />
        </template>
      </FormCentered>
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
import AppInput from './components/AppInput'
import AppTextarea from './components/AppTextarea'
import FormCentered from './components/FormCentered'

export default {
  name: 'App',
  components: {
    AppButton,
    AppHeader,
    AppInput,
    AppTextarea,
    FormCentered
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
