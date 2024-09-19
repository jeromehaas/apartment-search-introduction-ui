<script setup>

	// IMPORTS
	import './heading.scss';

  // SETUP PROPS
  const props = defineProps(['level', 'className']);

</script>

<template>
    <h1 v-if="level === 'h1'" :class="['heading', 'heading--h1',  props.className]">
      <slot />
    </h1>
      <h2 v-if="level === 'h2'" :class="['heading', 'heading--h2', props.className]">
      <slot />
    </h2>
    <h3 v-if="level === 'h3'" :class="['heading', 'heading--h3', props.className]">
      <slot />
    </h3>
</template>