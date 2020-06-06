<template>
  <div>
    <label class="input-label" :for="id">{{ label }}</label>
    <input
      :id="id"
      :name="id"
      type="text"
      :value="value"
      @input="handleInput($event)"
    />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'
import { Prop, Emit } from 'vue-property-decorator'

@Component
export default class VueTextInput extends Vue {
  @Prop({ type: String, required: true }) readonly id!: string
  @Prop({ type: String, required: true }) readonly label!: string
  @Prop({ type: String, required: false, default: '' }) readonly value!: string

  @Emit()
  private valueChanged(_newValue: string) {}

  private handleInput(event: InputEvent): void {
    this.valueChanged((event.target as HTMLInputElement).value)
  }
}
</script>

<style scoped>
.input-label {
  color: red;
}
</style>
