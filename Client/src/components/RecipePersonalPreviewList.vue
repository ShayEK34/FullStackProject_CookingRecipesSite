<template>
  <b-container>
    <br />
    <h3 class="title">{{ title }}:</h3>
    <b-row v-for="r in recipes" :key="r.id">
      <b-col>
        <b-card
          class="card"
          style="max-width: 35rem;max-height:50rem;border-color: rgb(247, 206, 168); border-style: solid;border-width: 15px; color:red"
        >
          <RecipePersonalPreview class="recipePreview" :recipe="r" />
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import RecipePersonalPreview from "./RecipePersonalPreview.vue";
export default {
  name: "RecipePersonalPreviewList",
  components: {
    RecipePersonalPreview,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    recipes: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.container {
  min-height: 400px;
}

.title {
  font-size: 32pt;
  font-weight: bold;
  -webkit-text-stroke: 2px black; /* width and color */
  font-family: "Comic Sans MS", cursive, sans-serif;
  color: whitesmoke;
  text-align: center;
}
.card {
  background: rgb(247, 239, 239);
}
</style>
