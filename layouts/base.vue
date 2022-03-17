<template>
  <div class="overflow-hidden">
    <div
      class="px-10 md:px-20 py-5 bg-blue-800 flex justify-between items-center"
    >
      <span class="flex items-center">
        <img class="w-12" :src="require(`~/assets/logo.svg`)" alt="logo" />
        <p class="text-white text-xl font-bold ml-3">SIObat</p>
      </span>
      <nuxt-link to="/" class="text-white font-semibold"> Beranda </nuxt-link>
    </div>
    <Nuxt />
    <div class="py-2 bg-blue-800 flex justify-center items-center">
      <p class="text-white text-xl font-bold ml-3">
        Made with &#10084;&#65039; from SV
      </p>
    </div>
  </div>
</template>
<script>
export default {
  name: "Base",
};
</script>
