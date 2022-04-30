<template>
  <div>
    <div v-for="question in setupQuestions" :key="question.prompt">
      <h2>{{ question.prompt }}</h2>
      <BaseButton
        v-for="answer in question.answers"
        :key="answer.answerText"
        :buttonText="answer.answerText"
        :buttonValue="answer.value"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import BaseButton from "./BaseButton.vue";
import { Questions } from "../quiz.json";
export default defineComponent({
  components: { BaseButton },
  setup() {
    const setupQuestions = Questions;
    return {
      setupQuestions,
    };
  },
});
</script>