<script setup lang="ts">
import AppButton from './components/AppButton.vue';
</script>

<template>
  <main>
    <div>
      <h1 class="mb-10">
        Using Dynamic components to build custom buttons in Vue Composition API
      </h1>

      <AppButton :style="{bgColor: '#000',color:'#fff', width: '500px'}">Normal button</AppButton>
      <AppButton :href="'!#'" >Linked button</AppButton>
    </div>
  </main>
</template>

<style scoped>
main {
  max-width: 1260px;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;

  text-align: center;
}

.mb-10 {
  margin-bottom: 10px;
}
</style>
