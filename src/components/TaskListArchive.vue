<template>
  <DetailsPopup style="position: absolute; top: 12px; right: 10px" ref="popup">
    <template v-slot:content v-if="board && list">
      <h4>Do you want to archive {{ list.name }} list?</h4>
      <button
        class="btn btn-sm btn-danger"
        @click="handleTaskListArchive(list)"
      >
        Yes, please.
      </button>
    </template>
  </DetailsPopup>
</template>

<script>
import DetailsPopup from "@/components/DetailsPopup";

export default {
  components: {
    DetailsPopup
  }
};
</script>
