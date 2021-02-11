<template lang="">
  <input
    placeholder="Type something to search for awsome gif"
    v-model="keyword"
    @input="onInput"
  />
</template>
<script>
export default {
  name: "Search",
  data() {
    return {
      keywords: "",
    };
  },
  methods: {
    onInput: function() {
      fetch(
        "https://api.giphy.com/v1/gifs/search?api_key=psgI3vxe9WKiLe7ZsE3GSVtCYgLUMzsC&q="
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
        });
    },
  },
};
//psgI3vxe9WKiLe7ZsE3GSVtCYgLUMzsC
</script>
<style scoped></style>
