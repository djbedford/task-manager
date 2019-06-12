<template>
  <DetailsPopup ref="restoreListPopup" v-show="this.activeBoard">
    <template v-slot:handle>
      <span class="nav-item btn btn-sm btn-app mr-2">
        rchived Lists ({{ archivedLists.length }})
      </span>
    </template>
    <template v-slot:content>
      <h4>Restore your lists for {{ boardName }}</h4>
      <ul class="list-group mb-2">
        <li
          v-for="list in archivedLists"
          :key="list.id"
          class="list-group-item d-flex justify-content-between align-items-center"
        >
          <label>
            {{ list.name }} <small>({{ list.items.length }} items)</small>
          </label>
          <button
            class="btn btn-sm btn-success"
            @click="handleTaskListRestore(list)"
          >
            Restore
          </button>
        </li>
        <li class="list-group-item" v-show="archivedLists.length == 0">
          Nothing to restore
        </li>
      </ul>
      <button class="btn btn-sm btn-app" @click="close">Done</button>
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
