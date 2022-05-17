<template>
  <v-navigation-drawer absolute>
    <FoldersList
      :folders="folders"
      :active-folder-id="activeFolderId"
      @setActiveFolderId="handleSetActiveFolderId"
    />
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
    activeFolderId: {
      type: Number,
      required: true,
    },
  },
  methods: {
    handleSetActiveFolderId(folderId) {
      this.$emit('setActiveFolderId', folderId);
    }
  }
};
</script>
