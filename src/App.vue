<script setup>
import { RouterView } from "vue-router";

import SideBarVue from "./components/SideBar.vue";
</script>

<template>
  <div class="flex">
    <SideBarVue />
    <div>
      <RouterView />
    </div>
  </div>
</template>

<style></style>
