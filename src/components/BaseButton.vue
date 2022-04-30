<template>
  <button class="btn" @click="$emit('click', buttonValue)">
    {{ buttonText }}
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  props: {
    buttonText: {
      type: String,
      required: true,
    },
    buttonValue: {
      type: Boolean,
      required: true,
    },
  },
});
</script>
