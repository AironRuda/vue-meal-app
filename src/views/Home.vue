<template>
  <div class="flex p-8 flex-col items-center justify-center">
    <input
      type="text"
      class="rounded border-2 border-gray-200 w-full"
      placeholder="Search for meals"
    />
    <div class="flex gap-2 mt-2">
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
  </div>
</template>

<script setup>
import { computed, onMounted, ref } from "vue";
import store from "../store";
import axiosClient from "../axiosClient.js";

const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("");
const ingredients = ref([]);

onMounted(async () => {
  const response = await axiosClient.get("/list.php?i=list");
  ingredients.value = response.data;
  console.log(response.data);
});
</script>
