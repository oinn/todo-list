<template>
  <v-main>
    <v-container>
      <TaskList :tasks="activeFolderTasks"/>
    </v-container>
  </v-main>
</template>

<script>
import TaskList from '@/components/TaskList.vue';

export default {
  name: 'AppContent',
  components: { TaskList },
  props: {
    folders: {
      type: Array,
      required: true,
    },
    activeFolderName: {
      type: String,
      required: true,
    },
  },
  computed: {
    activeFolderTasks() {
      const activeFolder = this.folders.find((folder) => folder.name === this.activeFolderName);
      return activeFolder?.tasks || [];
    },
  }
};
</script>
