<script setup>
const id = ref(1);
const {
  data: product,
  pending,
  error,
} = await useFetch(() => `https://dummyjson.com/products/${id.value}`);

function handleClick(shift) {
  id.value += shift;
}
</script>

<template>
  <div>
    <p>
      Result of <code>https://dummyjson.com/products/</code
      ><input type="number" v-model="id" />
    </p>
    <p>
      <button @click="handleClick(-1)">Previous</button> -
      <button @click="handleClick(+1)">Next</button>
    </p>
    <p v-if="pending">Fetching...</p>
    <pre v-else-if="error">{{ error }}</pre>
    <pre v-else>{{ product }}</pre>
    <NuxtLink to="/">Back home</NuxtLink>
  </div>
</template>
