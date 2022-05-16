<template>
  <v-list active-strategy="multiple" density="compact">
    <v-list-item
      v-for="(task, index) in tasks" :key="index"
      :value="task"
    >
      <template #default="{ isActive }">
        <v-list-item-avatar start>
          <v-checkbox :model-value="isActive" hide-details></v-checkbox>
        </v-list-item-avatar>

        <v-list-item-header>
          <v-list-item-title>{{ task.text }}</v-list-item-title>
        </v-list-item-header>
      </template>
    </v-list-item>
  </v-list>
</template>

<script>
export default {
  name: 'TaskList',
  props: {
    tasks: {
      type: Array,
      default: []
    },
  },
};
</script>
