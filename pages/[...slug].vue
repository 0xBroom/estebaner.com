<template>
  <main>
    <NuxtLink to="/">Back to home</NuxtLink>
    <ContentRenderer v-if="data" :value="data" />
  </main>
</template>

<script setup>
const { path } = useRoute();
const { data } = await useAsyncData(() =>
  queryCollection("content").path(`${path}`).first()
);
</script>
