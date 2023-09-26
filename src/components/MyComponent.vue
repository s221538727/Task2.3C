<!-- MyComponent.vue -->
<template>
    <div>
      <p>{{ message }}</p>
      <button @click="emitCustomEvent">Emit Event</button>
    </div>
  </template>
  
  <script>
  import {  defineEmits } from "vue";
  
  export default {
    props: {
      message: String,
    },
    setup() {
      const emit = defineEmits();
      const emitCustomEvent = () => {
        emit("custom-event", "Custom event data from child!");
      };
  
      return {
        emitCustomEvent,
      };
    },
  };
  </script>