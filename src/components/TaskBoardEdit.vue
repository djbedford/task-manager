<template>
  <DetailsPopup
    ref="newBoardPopup"
    v-show="!this.activeBoard"
    @popup-toggled="handlePopupToggled"
  >
    <template v-slot:handle>
      <span class="nav-item btn btn-sm btn-app mr-2">+ New Board</span>
    </template>
    <template v-slot:content>
      <form>
        <h4>{{ heading }}</h4>
        <input
          name="boardName"
          type="text"
          class="form-control my-1"
          v-model.trim="boardForm.name"
          v-validate="'required'"
          data-vv-as="Board Name"
          placeholder="Enter your board name"
        />
        <small class="text-danger" style="display: block;">
          {{ errors.first("boardName") }}
        </small>
        <textarea
          name="boardDescription"
          rows="2"
          class="form-control my-1"
          v-model.trim="boardForm.description"
          v-validate="'required'"
          data-vv-as="Board Description"
          placeholder="Enter your board description"
        ></textarea>
        <small class="text-danger" style="display: block;">
          {{ errors.first("boardDescription") }}
        </small>
        <button
          class="btn btn-sm btn-app mt-2"
          @click.prevent="handleSaveBoard"
        >
          Save Board
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
