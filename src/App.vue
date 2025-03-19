<script setup lang="ts">
import { darkTheme, lightTheme } from "naive-ui";
import { test_log } from "@/utils";
import HelloWorld from "./components/HelloWorld.vue";
import { useDark, useToggle } from "@vueuse/core";
const isDark = useDark();
const toggleDark = useToggle(isDark);
const backGroundColor = computed(() => {
  return isDark.value ? "#000" : "#fff";
});
test_log();
</script>

<template>
  <n-config-provider :theme="isDark ? darkTheme : lightTheme">
    <n-message-provider>
      <div
        class="flex gap-2 items-center justify-center h-[100vh]"
        :style="{ backgroundColor: backGroundColor }"
      >
        <HelloWorld />
        <n-button @click="toggleDark()">toggle</n-button>
      </div>
    </n-message-provider>
  </n-config-provider>
</template>

<style scoped></style>
