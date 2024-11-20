<template>
  <div class="container text-center">
    <div class="row row-cols-2">
      <div class="col" v-for="(image, index) in images" :key="index">
        <img :src="image" class="img-thumbnail" alt="..." />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Quatuor",
  props: ["images"],
};
</script>

<style scoped>
.quatuor img {
  /* Styles pour disposer les images en grille */
}
</style>
