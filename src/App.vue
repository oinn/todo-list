<template>
  <v-app>
    <AppHeader/>
    <AppSidebar
      :folders="folders"
      :active-folder-id="activeFolderId"
      @setActiveFolderId="setActiveFolderId"
    />
    <AppContent
      :tasks="activeFolderTasks"
      @toggleCheckTackId="toggleCheckTackId"/>
  </v-app>
</template>

<script>
import AppSidebar from '@/components/AppSidebar.vue';
import AppHeader from '@/components/AppHeader.vue';
import AppContent from '@/components/AppContent.vue';

export default {
  name: 'App',
  components: { AppContent, AppSidebar, AppHeader },
  data() {
    return {
      folders: [
        {
          id: 1,
          name: 'Personal',
          icon: 'mdi-folder',
          tasks: [
            { id: 1, text: 'Personal task #1', isChecked: false },
            { id: 2, text: 'Personal task #3', isChecked: true },
            { id: 3, text: 'Personal task #3', isChecked: false }
          ]
        },
        {
          id: 2,
          name: 'Work',
          icon: 'mdi-file',
          tasks: [
            { id: 4, text: 'Work task #1', isChecked: false },
            { id: 5, text: 'Work task #3', isChecked: false },
            { id: 6, text: 'Work task #3', isChecked: false }
          ]
        },
      ],
      activeFolderId: 1,
    }
  },
  computed: {
    activeFolderTasks() {
      return this.folders.find((folder) => folder.id === this.activeFolderId)?.tasks || [];
    },
  },
  methods: {
    setActiveFolderId(folderId) {
      this.activeFolderId = folderId;
    },
    toggleCheckTackId(taskId) {
      this.folders = this.folders.map((folder) => ({
        ...folder,
        tasks: folder.tasks.map((task) => ({
          ...task,
          isChecked: task.id === taskId ? !task.isChecked: task.isChecked,
        })),
      }));
    }
  },
}
</script>
