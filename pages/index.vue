<template>
  <div class="shadow rounded p-10 pt-2 m-16">
    <input />
    <h1 class="text-2xl font-bold">Obat Berdasarkan Kategori</h1>
    <div class="mt-5 grid grid-cols-4 gap-4">
      <div
        v-for="(category, idx) in categories"
        :key="idx"
      >
        <button
          @click="onSearchCategory(category)"
          class="block border text-left w-full p-5 rounded-md flex items-center hover:border-blue-500"
        >
          <img class="w-12 mr-3" :src="category.image_url" :alt="category.slug" />
          <span> {{ category.attributes.name }} </span>
        </button>
      </div>
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
      this.$router.push(`${category.slug}`);
    },
  },
};
</script>
