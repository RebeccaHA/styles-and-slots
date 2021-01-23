<template>
  <div>
    <the-header></the-header>
    <button>Active Goals</button>
    <button>Manage Goals</button>
    <component></component>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import ActiveGoals from "./components/ActiveGoals.vue";
import ManageGoals from "./components/ManageGoals.vue";

export default {
  components: {
    TheHeader,
    ActiveGoals,
    ManageGoals
  },
  data() {
    return {
      selected: "active-goals",
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin"
      }
    };
  },
  methods: {
    setSelected(comp) {
      this.selected = comp;
    }
  }
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>