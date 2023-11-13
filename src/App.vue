<template>
  <div>
    <RouterView />
  </div>
</template>

<script>
import { useDark, useToggle } from "@vueuse/core";
export default {
  setup() {
    const isDark = useDark();
    const toggle = useToggle(isDark);
    return {
      isDark,
      toggle,
    };
  },
};  
</script>

<style></style>
