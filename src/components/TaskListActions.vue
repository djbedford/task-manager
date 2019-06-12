<template>
  <DetailsDropdown
    style="position: absolute; top: 12px; right: 10px"
    ref="dropdown"
  >
    <template v-slot:handle
      >...</template
    >
    <template v-slot:content>
      <label class="content-item" @click="showListEditPopup">Edit</label>
      <label class="content-item" @click="showArchiveListPopup">Archive</label>
    </template>
  </DetailsDropdown>
</template>

<script>
import DetailsDropdown from "@/components/DetailsDropdown";

export default {
  components: {
    DetailsDropdown
  }
};
</script>
