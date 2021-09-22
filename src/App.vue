<template>
  <div>
    <the-header></the-header>
    <button @click="setSelectedComponent('active-goals')">Active Goals</button>
    <button @click="setSelectedComponent('manage-goals')">Manage Goals</button>
    <!-- <ActiveGoals v-if="selectedComponente === 'active-goals'" />
    <manage-goals v-if="selectedComponente === 'manage-goals'"></manage-goals> -->
    <keep-alive>
      <component :is="selectedComponente"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
//import BadgeList from "./components/BadgeList.vue";
//import UserInfo from "./components/UserInfo.vue";
//import CourseGoal from "@/components/CourseGoal.vue";
import ActiveGoals from "@/components/ActiveGoals.vue";
import ManageGoals from "@/components/ManageGoals.vue";

export default {
  components: {
    TheHeader,
    /* BadgeList,
    UserInfo,
    CourseGoal, */
    ActiveGoals,
    ManageGoals,
  },
  data() {
    return {
      selectedComponente: "active-goals",
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponente = cmp;
    },
  },
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
