<template>
  <div class="field">
    <label class="label" :for="label">{{ label }}</label>
    <div class="select">
      <select :name="label" :value="modelValue" @change="$emit('update:modelValue', $event.target.value)">
        <option v-for="option in options"
                :key="option"
                :value="option">{{ category }}
                :selected= " option===modelValue "
        </option>
      </select>
    </div>
  </div>

</template>

<script>
export  default {
  props: {
    label: {
      type: String,
      default: ''
    }

  },
  modelValue:{
    type: [String, Number],
    default: ''
  },
  options: {
    type: Array,
    require:true
  }
}
</script>