<template>
  <v-theme-provider theme="dark" with-background>
    <v-app-bar height="56" flat color="grey">
      <v-app-bar-title>Todo List</v-app-bar-title>

      <v-text-field
        placeholder="Fast task"
        variant="outlined"
        hide-details density="compact"
        bg-color="white"
      />

      <v-spacer/>
    </v-app-bar>
  </v-theme-provider>
</template>

<script>
export default {
  name: 'AppHeader',
};
</script>
