<template>
  <v-list density="compact">
    <v-list-subheader>FOLDERS</v-list-subheader>

    <v-list-item
      v-for="folder in folders" :key="folder.id"
      :active="folder.id === activeFolderId"
      @click="handleItemClick(folder.id)"
    >
      <v-list-item-avatar start>
        <v-icon :icon="folder.icon"/>
      </v-list-item-avatar>
      <v-list-item-title>{{ folder.name }}</v-list-item-title>
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
    activeFolderId: {
      type: Number,
      required: true,
    },
  },
  methods: {
    handleItemClick(folderId) {
      this.$emit('setActiveFolderId', folderId);
    }
  }
}
</script>
