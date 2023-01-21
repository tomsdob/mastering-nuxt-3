<script lang="ts" setup>
defineProps<{ videoId: string }>();
</script>

<template>
  <iframe
    class="max-w-full"
    width="560"
    height="315"
    :src="`https://player.vimeo.com/video/${videoId}`"
    title="Video player"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen
  ></iframe>
</template>
