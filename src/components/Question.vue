<template>
  <div>
    <div v-for="question in setupQuestions" :key="question.prompt">
      <h2>{{ question.prompt }}</h2>
      <p>{{ points }}</p>
      <BaseButton
        v-for="answer in question.answers"
        :key="answer.answerText"
        :buttonText="answer.answerText"
        :buttonValue="answer.value"
        @pressed="addPoints($event)"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, computed } from "vue";
import BaseButton from "./BaseButton.vue";
import { Questions } from "../quiz.json";
export default defineComponent({
  components: { BaseButton },
  setup() {
    const setupQuestions = Questions;
    let points = ref(0);
    function addPoints(event) {
      if (event == true) {
        points.value++;
      }
    }
    return {
      setupQuestions,
      points,
      addPoints,
    };
  },
});
</script>