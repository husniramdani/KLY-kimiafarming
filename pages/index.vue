<template>
  <div class="shadow rounded p-10 m-16">
    <input />
    <div v-for="(category, idx) in categories" :key="idx">
      <button @click="onSearchCategory(category)">{{ category.slug }}</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "home",
  layout: "base",
  async asyncData({ $axios }) {
    const categories = await $axios
      .$get("/medicine/categories")
      .then((res) => res.results);
    return { categories };
  },
  methods: {
    onSearchCategory(category) {
      this.$router.push({
        name: "category",
        path: "category",
        params: {
          category: category.slug,
        },
      });
    },
  },
};
</script>
