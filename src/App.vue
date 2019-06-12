<template>
  <div id="app" class="container-fluid">
    <AppHeader></AppHeader>
    <transition name="page" mode="out-in" v-if="!isLoading">
      <router-view></router-view>
    </transition>
    <AppLoadingIndicator></AppLoadingIndicator>
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader";
import AppLoadingIndicator from "@/components/AppLoadingIndicator";

export default {
  components: {
    AppHeader,
    AppLoadingIndicator
  }
};
</script>
