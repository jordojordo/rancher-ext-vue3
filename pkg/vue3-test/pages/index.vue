<script setup lang="ts">
import Code from '../components/Code.vue';

const message = 'Hello, World!';
</script>

<template>
  <div>
    <h1>{{ message }}</h1>
    <Code />
  </div>
</template>