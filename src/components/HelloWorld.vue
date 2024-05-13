<script lang="ts">
import { defineComponent } from 'vue';

const test = {
  props: {
    modelValue: {
      type: Object,
      default: () => {}
    }
  },
  computed: {
    value: {
      get() {
        return this.modelValue;
      },
      set(value) {
        this.$emit('update:modelValue', value);
      }
    }
  }
};

export default defineComponent({
  mixins: [test],
})
</script>

<template>
  <div class="greetings">
    <h1 class="green">Hello {{ value }}</h1>

    <input v-model="value">
    
    <div>
      {{ JSON.stringify(value) }}
    </div>
    
    <h3>
      You’ve successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
