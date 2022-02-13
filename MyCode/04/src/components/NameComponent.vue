<template>
  <p>{{ firstName }} {{ lastName }}</p>
  <h2>{{ fullName }}</h2>
</template>
<script>
import { ref, computed } from "vue";
export default {
  name: "NameComponent",
  setup() {
    const firstName = ref("Wagner");
    const lastName = ref("Xu");
    const fullName = computed(() => `${firstName.value} ${lastName.value}`);
    return {
      firstName,
      lastName,
      fullName,
    };
  },
};
</script>