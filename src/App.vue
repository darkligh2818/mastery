<template>
  <nav>
    <div class="p-4 flex justify-center space-x-10 bg-gradient-to-r from-green-200 to-gray-100 shadow-lg shadow-green-200 opacity-1">
      <router-link to="/" class="text-xl font-serif uppercase font-bold text-green-600">Home</router-link>
      <router-link to="/about" class="text-xl font-serif uppercase font-bold text-green-600">About</router-link>
    </div>
  </nav>
  <router-view></router-view>
</template>


<script>
export default {
  name: 'App'
}
</script>