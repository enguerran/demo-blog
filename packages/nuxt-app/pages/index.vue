<script setup>
import SayHi from "vue-components/SayHi.vue";
import { useMouse } from "vue-composables/useMouse";
const { data } = await useFetch("/api/hello");

const { x, y } = useMouse();
</script>

<template>
  <div>
    <p>Result of <code>/api/hello</code>:</p>
    <pre>{{ data }}</pre>
    <p><NuxtLink to="/external">Visit /external</NuxtLink></p>
    <p><NuxtLink to="/component">Visit /component</NuxtLink></p>
    <SayHi name="Alice" />
    <div>Mouse position is at: {{ x }}, {{ y }}</div>
  </div>
</template>
