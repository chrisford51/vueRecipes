<template>
  <div class="index container">
    <div class="card" v-for="recipe in recipes" :key="recipe.id">
      <div class="card-content">
        <i class="material-icons delete" @click="deleteRecipe(recipe.id)">delete</i>
        <h2 class="indigo-text">{{ recipe.title }}</h2>
        <ul class="ingredients">
          <li v-for="(ing, index) in recipe.ingredients" :key="index">
            <span class="chip">{{ ing }}</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Index",
  data() {
    return {
      recipes: [
        {
          title: "Vue Food 1",
          slug: "vue-food-1",
          ingredients: ["food item 1", "item 2", "item 3"],
          id: "1"
        },
        {
          title: "Vue Food 2",
          slug: "vue-food-2",
          ingredients: ["food item 1", "item 2", "item 3", "item 4"],
          id: "2"
        },
        {
          title: "Vue Food 3",
          slug: "vue-food-1",
          ingredients: ["food item 1", "item 2", "item 3"],
          id: "3"
        },
        {
          title: "Vue Food 4",
          slug: "vue-food-1",
          ingredients: ["food item 1", "item 2", "item 3"],
          id: "4"
        }
      ]
    };
  },
  methods: {
    deleteRecipe(id) {
      this.recipes = this.recipes.filter(recipe => {
        return recipe.id != id;
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.index {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 30px;
  margin-top: 60px;
}

.index h2 {
  font-size: 1.8em;
  text-align: center;
  margin-top: 0;
}
.index .ingredients {
  margin: 30px auto;
}

.index .ingredients li {
  display: inline-block;
}

.index .delete {
  position: absolute;
  top: 4px;
  right: 4px;
  cursor: pointer;
  color: #aaa;
  font-size: 1.4em;
}
</style>
