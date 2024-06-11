<template>
  <q-page>
    <q-list bordered separator>
      <task
        v-for="(task, id) in tasks"
        :key="id"
        :task="task"
        :id="id"
      />
    </q-list>
  </q-page>
</template>
<div class="absolute-bottom q-mb-md text-center">
  <q-btn round color="primary" fab icon="add" size="18px" @click="showAddtask = true" />
</div>

<q-dialog v-model="showAddtask"></q-dialog>
<script>
import Task from 'components/TaskComponent.vue'
import { mapGetters } from 'vuex';

export default {
  name: 'PageTodo',
  components: {
    Task
  },
  data() {
    return {
      showAddtask: false

    }
  },
  computed: {
      ...mapGetters('tasks', ['tasks']),
  }
}
</script>
