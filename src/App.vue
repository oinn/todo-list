<template>
  <v-app>
    <AppHeader/>
    <AppSidebar :folders="folders" @change="changeActiveFolder"/>
    <AppContent :folders="folders" :activeFolderName="activeFolderName"/>
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
          name: 'Personal',
          tasks: [
            { text: 'Task #1', isChecked: false },
            { text: 'Task #2', isChecked: false },
            { text: 'Task #3', isChecked: false }
          ]
        },
        {
          name: 'Work',
          tasks: [
            { text: 'Task #1', isChecked: false },
            { text: 'Task #2', isChecked: false },
            { text: 'Task #3', isChecked: false }
          ]
        }
      ],
      activeFolderName: 'Personal'
    }
  },
  methods: {
    changeActiveFolder(folderName) {
      this.activeFolderName = folderName;
    }
  }
}
</script>
