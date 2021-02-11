<template>
  <search />
  <gif-list :gifs="gifs" />
</template>

<script>
import Search from "@/components/Search";
import GifList from "@/components/GifList.vue";
export default {
  name: "App",
  components: {
    Search,
    GifList,
  },
  data() {
    return {
      gifs: [],
    };
  },
};
</script>

<style></style>
