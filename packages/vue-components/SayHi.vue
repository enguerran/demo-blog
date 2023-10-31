<script lang="ts" setup>
const props = defineProps(["name"]);
</script>

<template>
  <div>Hi {{ props.name }}!</div>
</template>
