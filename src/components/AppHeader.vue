<template>
  <nav class="navbar navbar-light bg-faded">
    <router-link to="/" class="navbar-brand">
      <label>
        Kanban Board
        <span class="text-uppercase" v-show="this.activeBoard">
          : {{ boardName }}
        </span>
      </label>
    </router-link>
    <div class="d-flex justify-content-end" v-if="!isLoading">
      <TaskListRestore></TaskListRestore>
      <TaskListEdit></TaskListEdit>
      <TaskBoardEdit></TaskBoardEdit>
      <TaskListArchive></TaskListArchive>
    </div>
  </nav>
</template>

<script>
import TaskListRestore from "@/components/TaskListRestore";
import TaskListEdit from "@/components/TaskListEdit";
import TaskBoardEdit from "@/components/TaskBoardEdit";
import TaskListArchive from "@/components/TaskListArchive";

export default {
  components: {
    TaskListRestore,
    TaskListEdit,
    TaskBoardEdit,
    TaskListArchive
  }
};
</script>
