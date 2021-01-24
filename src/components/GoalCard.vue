<template>
  <div>
    <h2>Goals</h2>
    <base-card>
      <ul>
        <li v-for="goal in goals" :key="goal">{{goal}}</li>
      </ul>
    </base-card>
  </div>
</template>

<script>
import BaseCard from "./BaseCard";
export default {
  components: {
    BaseCard
  },
  props: {
    goals: {
      type: Array
    }
  }
};
</script>