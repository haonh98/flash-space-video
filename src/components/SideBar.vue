<script setup>
import { ref } from "vue";
import { RouterLink } from "vue-router";
import {
  HomeIcon,
  PhotographIcon,
  FilmIcon,
  VideoCameraIcon,
} from "@heroicons/vue/solid";
const isToggle = ref(false);
function toggleSidebar() {
  isToggle.value = !isToggle.value;
}
const menus = [
  { path: "/", name: "Trang chủ", icon: HomeIcon },
  { path: "/phim-le", name: "Phim lẻ", icon: PhotographIcon },
  { path: "/phim-bo", name: "Phim bộ", icon: FilmIcon },
  { path: "/phim-hoat-hinh", name: "Phim hoạt hình", icon: VideoCameraIcon },
];
</script>
<template>
  <div
    class="min-h-screen shadow-lg overflow-hidden flex flex-col transition-all duration-300"
    :class="isToggle ? 'w-[236px]' : 'w-[72px] items-center'"
  >
    <a href="/" class="flex items-center text-cyan-700 space-x-2 py-8 px-4">
      <img
        class="h-10 w-10"
        src="../assets/images/logo.png"
        alt="Flash Space"
      />
      <span v-show="isToggle" class="text-lg uppercase font-light"
        >Flash <b class="font-extrabold">space</b></span
      >
    </a>
    <div class="border-b border-gray-100"></div>

    <!-- Menu -->
    <div
      class="px-3 space-y-4 flex flex-col"
      :class="isToggle ? 'mt-8' : 'items-center mt-[60px]'"
    >
      <h4 v-show="isToggle">menu</h4>
      <router-link
        class="flex items-center space-x-6 py-1 rounded-lg text-gray-900"
        :class="isToggle ? 'px-3' : 'px-1'"
        to="/"
      >
        <HomeIcon class="h-6 w-6" />
        <span v-show="isToggle" class="text-sm font-medium">Home</span>
      </router-link>
    </div>
    <button @click="toggleSidebar">Toggle</button>
  </div>
</template>
<style scoped>
.router-link-active,
.router-link-exact-active {
  @apply bg-cyan-700 text-white;
}
</style>
