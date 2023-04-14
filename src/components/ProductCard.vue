<script>
export default {
  name: "ProductCard",

  props: {
    img: String,
    series: String,
  },
};
</script>

<template>
  <div class="card">
    <img :src="img" alt="" />
    <p>{{ series }}</p>
  </div>
</template>

<style scoped lang="scss">
.card {
  width: calc(100% / 6 - 20px);
  margin: 10px;
  img {
    height: 70%;
  }
  p {
    color: white;
    text-transform: uppercase;
    margin: 20px 0;
  }
}
</style>
