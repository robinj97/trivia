<template>
  <h1>Are you a true One Piece Fan?</h1>
  <Question />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import BaseButton from "./components/BaseButton.vue";
import Question from "./components/Question.vue";
export default defineComponent({
  components: { BaseButton, Question },
  setup() {},
});
</script>

