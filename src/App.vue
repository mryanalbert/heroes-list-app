<script>
import AppHeader from "./components/AppHeader.vue";
import Heroes from "./components/Heroes.vue";
export default {
  // COMPONENTS
  components: {
    AppHeader,
    Heroes,
  },
};
</script>

<template>
  <AppHeader />
  <div class="w-full flex">
    <Heroes />
  </div>
</template>
