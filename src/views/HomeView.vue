<template>
  <div class="bg-gray-200 m-8 rounded-xl shadow-lg">
    <div class="absolute right-32 top-28 py-3 px-6 bg-blue-600 text-white font-serif rounded shadow-lg border border-white">Cart({{ cart }})</div>
    <div>
      <div class="flex py-8 px-10 space-x-10">
        <div>
          <img class="w-80 h-80" v-bind:src="image" alt="das">
        </div>
        <div>
          <h1 class="text-3xl font-bold font-serif uppercase">{{ product }}</h1>
          <p v-if="inStock" class="mt-8">In Stock</p>
          <p v-else>Out of Stock</p>
          <ul>
            <li v-for="detail in details" :key="detail">{{ detail }}</li>
          </ul>
          <div class="cursor-pointer text-xl font-serif" v-for="variant in variants" :key="variant.id" @mouseover="updateImage(variant.image)">{{ variant.color }}</div>
          <button @click="addToCart()" class="mt-10 py-2 px-5 bg-green-400 hover:bg-green-500 duration-300 text-white font-serif rounded-lg border border-white shadow-lg" >Add to Cart</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
  data() {
    return {
      cart: 0,
      product: 'Socks',
      inStock: true,
      details: ['50% cotton', '30% wool', '20% polyester'],
      image: 'socks_green.jpg',
      variants: [
        {
          id: 2234,
          color: 'green',
          image: 'socks_green.jpg',
        },
        {
          id: 2235,
          color: 'blue',
          image: 'socks_blue.jpg',
        }
      ]
    }
  },
  methods: {
    addToCart() {
      this.cart += 1;
    },
    updateImage(variantImage) {
      this.image = variantImage;
    }
  }
}
</script>
