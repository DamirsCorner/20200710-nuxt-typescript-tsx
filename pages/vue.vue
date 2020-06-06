<template>
  <div>
    <VueTextInput id="input" label="Input: " @value-changed="value = $event" />
    <div>{{ value }}</div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from 'vue-class-component'
import VueTextInput from '~/components/VueTextInput.vue'

@Component({
  components: { VueTextInput }
})
export default class VuePage extends Vue {
  value = ''
}
</script>
