<template>
  <v-main>
    <v-container>
      <TaskList :tasks="tasks" @toggleCheckTackId="handleToggleCheckTackId"/>
    </v-container>
  </v-main>
</template>

<script>
import TaskList from '@/components/TaskList.vue';

export default {
  name: 'AppContent',
  components: { TaskList },
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },
  methods: {
    handleToggleCheckTackId(taskId) {
      this.$emit('toggleCheckTackId', taskId)
    }
  }
};
</script>
