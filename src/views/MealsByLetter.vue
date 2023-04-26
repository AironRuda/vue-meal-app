<template>
  <div class="flex justify-center gap-2 mt-2">
    <router-link
      :to="{
        name: 'byletter',
        params: { letter },
      }"
      :key="letter"
      v-for="letter of letters"
    >
      {{ letter }}
    </router-link>
  </div>
</template>

<script setup>
const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("");
</script>
