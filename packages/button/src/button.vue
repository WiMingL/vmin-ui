<template>
  <button class="vm-btn"
          :class="{'vm-disable': disabled}"
          :style="{
            fontSize: fontSize + 'px'
          }"
          :disabled="disabled"
          @click="click">
    {{ value }}
  </button>
</template>

<script>
import './button.css'
export default {
  name: 'VmButton',
  props: {
    disabled: {
      type: Boolean,
      default: false
    },
    value: {
      type: String,
      default: '按钮'
    },
    fontSize: {
      type: Number,
      default: 14
    },
    load: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    click() {
      this.$emit('click')
    }
  }
}
</script>

<style>
</style>