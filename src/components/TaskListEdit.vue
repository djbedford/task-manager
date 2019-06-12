<template>
  <DetailsPopup
    ref="newListPopup"
    v-show="this.activeBoard"
    @popup-toggled="handlePopupToggled"
  >
    <template v-slot:handle>
      <span class="nav-item btn btn-sm btn-app mr-2">+ New List</span>
    </template>
    <template v-slot:content>
      <form>
        <h4>{{ heading }}</h4>
        <input
          name="listName"
          type="text"
          class="form-control my-1"
          v-model.trim="listForm.name"
          v-validate="'required'"
          data-vv-as="List Name"
          placeholder="Enter your list name"
        />
        <small class="text-danger" style="display: block;">
          {{ errors.first("listName") }}
        </small>
        <button
          class="btn btn-sm btn-app mt-2"
          @click.prevent="handleTaskListSave"
        >
          Save List
        </button>
      </form>
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
