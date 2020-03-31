<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-model="todo.completed" />
      {{todo.title}}
      <button @click="$emit('del-todo', todo.id)" class="del">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "Todoitem",
  props: ["todo"]
};
</script>

<style scoped>
.todo-item {
  box-sizing: border-box;
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
  padding-inline-start: 0;
  margin-block-end: 0;
  text-overflow: ellipsis;
}
.is-complete {
  text-decoration: line-through;
}
.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>