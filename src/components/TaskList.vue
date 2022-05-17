<template>
  <v-list active-strategy="multiple" density="compact">
    <v-list-item v-for="task in tasks" :key="task.id">
        <v-list-item-avatar>
          <v-checkbox :modelValue="task.isChecked" hide-details @click="handleCheckTask(task.id)"/>
        </v-list-item-avatar>

      <v-list-item-header>
        <v-list-item-title>{{ task.text }}</v-list-item-title>
      </v-list-item-header>
    </v-list-item>
  </v-list>
</template>

<script>
export default {
  name: 'TaskList',
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },
  methods: {
    handleCheckTask(taskId) {
      this.$emit('toggleCheckTackId', taskId);
    }
  }
};
</script>
