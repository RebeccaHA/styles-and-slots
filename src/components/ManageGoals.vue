<template>
  <div>
    <h2>Manage Goals</h2>
    <input type="text" ref="goal" />
    <button @click="setGoal">Set goal</button>
    <teleport to="#app">
    <error-message v-if="invalidInput">
      <h2>Invalid input</h2>
      <p>Please enter input into the box</p>
      <button @click="errorRecieved">Close</button>
    </error-message>
</teleport>
    <goal-card :goals="goals"></goal-card>
  </div>
</template>

<script>
import ErrorMessage from "./ErrorMessage";
import GoalCard from "./GoalCard";

export default {
  components: {
    ErrorMessage,
    GoalCard
  },
  data() {
    return {
      invalidInput: false,
      goals: []
    };
  },
  methods: {
    setGoal() {
      const enteredInput = this.$refs.goal.value;
      if (enteredInput === "") {
        this.invalidInput = true;
      } else {
        this.goals.push(enteredInput);
        this.$refs.goal.value = "";
      }
    },
    errorRecieved() {
      this.invalidInput = false;
    }
  }
};
</script>