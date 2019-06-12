<template>
  <div class="indicator text-center" v-if="isLoading">
    <svg
      width="135"
      height="140"
      viewBox="0 0 135 140"
      xmlns="http://www.w3.org/2000/svg"
      fill="#dc3545"
    ></svg>
    <h4>Loading...</h4>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  computed: {
    ...mapGetters({
      isLoading: "isLoading"
    })
  }
};
</script>
