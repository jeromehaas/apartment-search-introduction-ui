<script setup>

// IMPORTS
import './paragraph.scss';

// SETUP PROPS
const props = defineProps(['className']);

</script>

<template>
  <p class="paragraph" :class="className">
    <slot/>
  </p>
</template>