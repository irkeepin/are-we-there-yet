<!--
  Full-bleed photo background for a slide.

  Implements the deck's transition scheme (deck/brief.md → Animations):
  the photo shows at full strength first, then on the first click it fades
  (brightness + contrast drop) so the content chunk on top stays legible.

  Drive the fade from the slide with the global `$clicks`:
    <PhotoBg src="/images/PXL_xxx.png" :dimmed="$clicks > 0" />
-->
<script setup lang="ts">
defineProps<{ src: string; dimmed?: boolean }>()
</script>

<template>
  <div
    class="photo-bg absolute inset-0 z-0 bg-black bg-cover bg-center transition-all duration-700 ease-out"
    :style="{
      backgroundImage: `url(${src})`,
      filter: dimmed ? 'brightness(0.32) contrast(0.9) saturate(0.95)' : 'brightness(1) contrast(1)',
    }"
  />
</template>
