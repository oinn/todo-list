<template>
  <v-list density="compact">
    <v-list-subheader>FOLDERS</v-list-subheader>

    <v-list-item
      v-for="(folder, index) in foldersView" :key="index"
      :value="folder"
    >
      <v-list-item-avatar start>
        <v-icon :icon="folder.icon"></v-icon>
      </v-list-item-avatar>
      <v-list-item-title v-text="folder.name"></v-list-item-title>
    </v-list-item>
  </v-list>
</template>

<script>
export default {
  name: 'FoldersList',
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
    foldersView() {
      return this.folders.map(({ name }) => ({ name, icon: 'mdi-folder', }))
    }
  },
}
</script>
