<template>
  <search @gifs-fetched="onGifsFetched" />
  <gif-list :gifs="gifs" />
</template>

<script>
import Search from "@/components/Search";
import GifList from "@/components/GifList";
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
  methods: {
    onGifsFetched(result) {
      console.log(result);
      this.gifs = result.data;
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  padding: 50px;
}
#app {
  max-width: 800px;
  width: 100%;
  margin: 0 auto;
}
</style>
