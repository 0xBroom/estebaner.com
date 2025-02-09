<template>
  <div>
    <h1>Estebaner's website</h1>
    <nav>
      <ul v-if="data">
        <li v-for="item in data" :key="item.path">
          <NuxtLink :to="item.path">{{ item.title }}</NuxtLink>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script setup>
const { data } = await useAsyncData("navigation", () => {
  return queryCollectionNavigation("content");
});
</script>

<style scoped>
.container {
  justify-content: center;
}
</style>
