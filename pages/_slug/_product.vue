<template>
  <div class="shadow rounded p-10 pt-2 m-16">
    <!-- <NuxtLink to="./" >Back to product</NuxtLink > -->
    
    <div class="flex">
      <div>
        <img :src="product.image_url" :alt="product.slug" class="w-full" />
      </div>
      <div>
        <h2 class="text-2xl font-bold">{{ product.name }}</h2>
        <p>
          Rp.{{ product.min_price }} - Rp.{{ product.base_price }}
          {{ product.selling_unit }}
        </p>
        <hr class="my-4" />
        <h4 class="text-lg font-semibold">Kategori</h4>
        <div>
          <span v-for="(category, idx) in product.categories" :key="idx">
            {{ category.name }}
          </span>
        </div>
        <hr class="my-4" />
        <h4 class="text-lg font-semibold">Deskripsi</h4>
        <p>{{ product.description }}</p>
        <hr class="my-4" />
        <h4 class="text-lg font-semibold">Indikasi Umum</h4>
        <p>{{ product.general_indication }}</p>
        <hr class="my-4" />
        <h4 class="text-lg font-semibold">Komposisi</h4>
        <p>{{ product.composition }}</p>
        <hr class="my-4" />
        <h4 class="text-lg font-semibold">Dosis</h4>
        <p>{{ product.dosage }}</p>
        <hr class="my-4" />
        <h4 class="text-lg font-semibold">Aturan Pakai</h4>
        <p>{{ product.how_to_use }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "product",
  layout: "base",
  async asyncData({ $axios, params }) {
    const slug = params.slug;
    const product_slug = params.product || "";
    const product = await $axios
      .$get(`/medicine/detail/${product_slug}`)
      .then((res) => res);
    console.log(product);
    return { slug, product };
  },
  methods: {},
};
</script>
