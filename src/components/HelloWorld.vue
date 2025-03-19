<script setup lang="ts">
import { useMessage } from "naive-ui";

const message = useMessage();
const onClick = () => {
  message.success("test");
};
</script>

<template>
  <n-button @click="onClick"> test </n-button>
</template>

<style scoped></style>
