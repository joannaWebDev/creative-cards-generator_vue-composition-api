<template>
  <ul class="grid-wrapper">
    <li class="category_item" v-for="category in uniqueCategories" :key="category">
      <router-link :to="{ name: 'Category', params: { category } }">{{ category }}</router-link>
    </li>
  </ul>
</template>

<script>
import useCategory from '@/composables/useCategory';

export default {
  data() {
    return {};
  },
  setup() {
    const { uniqueCategories } = useCategory();

    return {
      uniqueCategories,
    };
  },
};
</script>

<style scoped>
@media (min-width: 600px) {
  .grid-wrapper {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 10px;
  }
}

@media (min-width: 1000px) {
  .grid-wrapper {
    grid-template-columns: repeat(3, 1fr);
  }
}

.category_item {
  background: linear-gradient(30deg,rgb(253, 207, 207), rgb(140, 140, 236));
  padding: 6rem 0;
}

ul {
  margin: 1rem;
}

li a {
  font-size: 20px;
}
</style>
