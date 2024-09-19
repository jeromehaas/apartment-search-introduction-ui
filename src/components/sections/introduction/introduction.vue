<script setup>

// IMPORTS
import './introduction.scss';
import Profile from '@/components/blocks/profile/profile.vue';
import Metadata from '@/components/blocks/metadata/metadata.vue';

</script>

<template>
  <div class="introduction">
    <Metadata class="introduction__metadata"/>
    <Profile class="introduction__profile" />
  </div>
</template>
