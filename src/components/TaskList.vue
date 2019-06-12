<template>
  <div class="col-3 list-column list-width">
    <div class="heading" :style="{ backgroundColor: list.headerColor }">
      <h4 class="heading-text text-center">{{ list.name }}</h4>
      <TaskListActions :board="board" :list="list"></TaskListActions>
    </div>
    <div class="cards cards-list">
      <draggable v-model="items" v-bind="dragOptions">
        <TaskListItem
          v-for="item in items"
          :item="item"
          :list="list"
          :board="board"
          :key="item.id"
          @item-edited="itemEdited"
          @item-cancelled="itemCancelled"
          @item-editing="itemEditing"
        ></TaskListItem>
      </draggable>
      <TaskListItem
        class="fixed-card"
        :item="defaultItem"
        :list="list"
        :board="board"
        @item-edited="itemEdited"
        @item-cancelled="itemCancelled"
        @item-editing="itemEditing"
      ></TaskListItem>
    </div>
  </div>
</template>

<script>
import TaskListActions from "@/components/TaskListActions";
import TaskListItem from "@/components/TaskListItem";

export default {
  components: {
    TaskListActions,
    TaskListItem
  }
};
</script>
