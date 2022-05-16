<template>
  <v-navigation-drawer absolute>
    <FoldersList :folders="folders" :activeFolderName="activeFolderName"/>
  </v-navigation-drawer>
</template>

<script>
import FoldersList from '@/components/FoldersList.vue';

export default {
  name: 'AppSidebar',
  components: { FoldersList },
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
};
</script>
