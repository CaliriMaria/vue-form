<template>
 <label class="radio">
   <input type="radio" :checked="value === modelValue" :value="value" @change="$emit('update:modelValue', value)">
   {{ label }}
 </label>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    },
    value: {
      type: [String, Number],
      require: true
    }
  }
}
</script>