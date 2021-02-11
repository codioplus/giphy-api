<template>
  <gif v-for="gif in gifs" :key="gif.id" :gif="gif" />
</template>
<script>
import Gif from "@/components/Gif.vue";
export default {
  components: { Gif },
  name: "GifList",
  props: {
    gifs: Array,
  },
};
</script>
<style scoped></style>
