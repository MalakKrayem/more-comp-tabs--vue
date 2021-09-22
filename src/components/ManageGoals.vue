<template>
  <h2>Manage Goals</h2>
  <input type="text" ref="goal" />
  <button @click="setGoal">Set Goal</button>
  <teleport to="body">
    <ErrorAlert v-if="inputIsInvalid">
      <h2>Input is Invalid!</h2>
      <p>Please enter your goal</p>
      <button @click="confirm">Ok</button>
    </ErrorAlert>
  </teleport>
  <div else v-for="goal in goals" :key="goal">
    {{ goal }}
  </div>
</template>

<script>
import ErrorAlert from "@/components/ErorrAlert.vue";
export default {
  components: {
    ErrorAlert,
  },
  data() {
    return {
      goals: [],
      inputIsInvalid: false,
    };
  },
  methods: {
    setGoal() {
      const enterd = this.$refs.goal.value;
      if (enterd === "") {
        this.inputIsInvalid = true;
      } else {
        this.inputIsInvalid = false;

        this.goals.push(enterd);
      }
    },
    confirm() {
      this.inputIsInvalid = false;
    },
  },
};
</script>

<style lang="scss" scoped></style>
