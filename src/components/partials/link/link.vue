<script setup>

// IMPORTS
import './link.scss';

// SETUP PROPS
const props = defineProps(['className', 'href']);

</script>

<template>
  <a class="link" :class="[props.className]" :href="props.href" target="_blank">
    <slot/>
  </a>
</template>