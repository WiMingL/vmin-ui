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

<style scoped>
.vm-btn {
  display: inline-block;
  padding: 5px 10px;
  color: #fff;
  background-color: #2d88ff;
  font-size: 14px;
  border: none;
  border-radius: 2px;
}

.vm-btn:not(.vm-disable):hover {
  background-color: #4093ff;
}

.vm-disable {
  background-color: #ccc;
  cursor: not-allowed;
}
</style>