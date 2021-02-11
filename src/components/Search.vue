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
      keyword: "",
      timeout: null,
    };
  },
  methods: {
    onInput: function() {
      clearTimeout(this.timeout);
      this.timeout = setTimeout(this.search, 500);
    },

    search: function() {
      fetch(
        `https://api.giphy.com/v1/gifs/search?api_key=psgI3vxe9WKiLe7ZsE3GSVtCYgLUMzsC&q=${this.keyword}&limit=9`
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result);
          this.$emit("gifs-fetched", result);
        });
    },
  },
};
//psgI3vxe9WKiLe7ZsE3GSVtCYgLUMzsC
</script>
<style scoped>
input {
  padding: 10px 16px;
  border-radius: 4px;
  font-size: 18px;
  border: 2px solid #5f5f5f;
  outline: 0;
  display: block;
  width: 100%;
}
input:focus {
  border-color: #009ad7;
}
</style>
