<script lang="ts">
import { defineComponent, type PropType } from 'vue';

interface Message {
  message: string;
}

export default defineComponent({
  props: {
    modelValue: {
      type: Object as PropType<Message>,
      required: true,
    }
  },
  data() {
    return {
      someVal: ''
    }
  }
})
</script>

<template>
  {{ JSON.stringify(modelValue) }}
  <br>
  {{  someVal }}
  <input :value="modelValue.message" @input="$emit('update:modelValue', { message: $event.target?.value }) ">
</template>
