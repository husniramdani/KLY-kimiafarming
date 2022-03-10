<template>
  <div class="shadow rounded p-10 m-16">
    Category
  </div>
</template>

<script>
export default {
  name: "category",
  layout: "base",
  async asyncData({ $axios }) {
    // const categories = await $axios
    //   .$get("/medicine/categories")
    //   .then((res) => res.results);
    // return { categories };
  },
  methods: {
    
  }
};
</script>
