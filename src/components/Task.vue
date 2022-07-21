<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      <span>{{ task.text }}</span>
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object,
  },
};
</script>

<style scope>
.fas {
  color: black;
  padding: 5px;
}
.task {
  background: #f4f4f4;
  margin: 10px 0;
  padding: 10px 20px;
  cursor: pointer;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.task.reminder {
  border-left: 3px solid rgb(21, 242, 21);
}
</style>
