
<template>
  <h1>{{ questionText }}</h1>
  <BaseButton v-for="(question, answer) in questionsList" />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import BaseButton from "./BaseButton.vue";
import { Questions } from "src/quiz.json";
export default defineComponent({
  components: { BaseButton },
  props: {
    questionText: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    const questionsList = Questions;
    const questionTextProp = props.questionText;
    return { questionTextProp, questionsList };
  },
});
</script>