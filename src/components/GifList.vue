<template>
  <div id="gifList">
    <gif v-for="gif in gifs" :key="gif.id" :gif="gif" />
  </div>
</template>
<script>
import Gif from "@/components/Gif";
export default {
  components: { Gif },
  name: "GifList",
  props: ["gifs"],
};
</script>
<style scoped>
#gifList {
  margin-top: 20px;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
</style>
