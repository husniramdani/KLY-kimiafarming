<template>
  <div class="shadow rounded p-10 pt-2 m-16">
    <input />
    <h1 class="text-2xl font-bold">Product</h1>
    <!-- <div class="mt-5 grid grid-cols-4 gap-4">
      <div
        v-for="(product, idx) in products"
        :key="idx"
      >
        <button
          class="block border text-left w-full p-5 rounded-md flex items-center hover:border-blue-500"
        >
          <img class="w-12 mr-3" :src="product.image_url" :alt="product.slug" />
          <span> {{ product.name }} </span>
        </button>
      </div>
    </div> -->
  </div>
</template>

<script>
export default {
  name: "product",
  layout: "base",
  // async asyncData({ $axios, route }) {
  //   const slug = route.query?.slug || "";
  //   const products = await $axios
  //     .$get(`/medicine/categories/${slug}/page/1`)
  //     .then((res) => res.result);
  //   return { products };
  // },
  methods: {
    
  }
};
</script>
