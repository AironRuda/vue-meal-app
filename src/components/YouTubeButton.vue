<template>
  <a
    :href="href"
    target="_blanck"
    class="p-3 rounded border-2 border-red-600 hover:bg-red-500 hover:text-white transition-colors"
  >
    <slot></slot>
  </a>
</template>
<script setup>
const props = defineProps({
  href: String,
});
</script>
