<template>
  <section>
    <BaseCard>
      <template v-slot:header>
        <header>
          <h3>{{ fullName }}</h3>
          <BaseBadge :type="role" :caption="role.toUpperCase()"></BaseBadge>
        </header>
      </template>
      <template v-slot:default>
        <p>{{ infoText }}</p>
      </template>
    </BaseCard>
  </section>
</template>

<script>
import BaseCard from "@/components/BaseCard.vue";
import BaseBadge from "@/components/BaseBadge.vue";

export default {
  components: {
    BaseCard,
    BaseBadge,
  },
  props: ["fullName", "infoText", "role"],
};
</script>

<style scoped>
section header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
