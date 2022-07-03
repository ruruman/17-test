<template>
  <div class="container">
    <h2>TODO LIST</h2>
    <h3>Add Item</h3>
    <p>
      <input
        id="new-task"
        type="text"
        placeholder="Add New Todo Here..."
        minlength="1"
        maxlength="48"
        v-model="newTodo"
        @keyup.enter="addTodo()"
      /><button @click="addTodo()">Add</button>
    </p>

    <h3>Todo</h3>
    <ul id="incomplete-tasks" v-for="(todo, index) in todoList" :key="index">
      <li v-if="!todo.isDone">
        <input type="checkbox" v-model="todo.isDone" /><label
          v-show="!todo.isEdit"
          >{{ todo.title }}</label
        ><input
          type="text"
          v-model="todo.title"
          v-show="todo.isEdit"
          @keyup.enter="edit(index)"
        /><button class="edit" @click="edit(index)">Edit</button
        ><button class="delete" @click="removeTodo(index)">Delete</button>
      </li>
    </ul>

    <h3>Completed</h3>
    <ul
      id="completed-tasks"
      v-for="(todo, index) in todoList"
      :key="'completed-' + index"
    >
      <li v-if="todo.isDone">
        <input type="checkbox" v-model="todo.isDone" /><label>{{
          todo.title
        }}</label>
        <button class="delete" @click="removeTodo(index)">Delete</button>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "TodoList",
  data() {
    return {
      todoList: [
        {
          title: "看書",
          isDone: true,
          isEdit: false,
        },
        {
          title: "衝浪",
          isDone: false,
          isEdit: true,
        },
        {
          title: "看怪奇物語",
          isDone: false,
          isEdit: false,
        },
      ],
      newTodo: "",
    };
  },
  methods: {
    addTodo() {
      const val = this.newTodo.trim();
      if (!val) {
        return;
      }
      const newItem = {
        title: val,
        isDone: false,
        isEdit: false,
      };
      this.todoList.push(newItem);
      this.newTodo = "";
    },
    removeTodo(index) {
      this.todoList.splice(index, 1);
    },
    edit(index) {
      this.todoList[index].isEdit = !this.todoList[index].isEdit;
    },
  },
};
</script>
<style scoped>
.container {
  border: 1px solid #aaa;
  display: block;
  width: 400px;
  margin: 10px auto 100px;
  background-color: #fff;
  padding: 0px 10px 10px 10px;
  border-radius: 10px;
}

h2 {
  text-align: center;
  padding-top: 10px;
  margin-bottom: 0px;
}

ul {
  margin: 0;
  padding: 0;
}

li * {
  float: left;
}

li,
h3 {
  clear: both;
  list-style: none;
}

input,
button {
  outline: none;
}

button {
  background: none;
  border: 0px;
  color: #888;
  font-size: 15px;
  width: 60px;
  margin: 10px 0 0;
  font-family: Lato, sans-serif;
  cursor: pointer;
}

button:hover {
  color: #333;
}

/* Heading */

h3,
label[for="new-task"] {
  color: #333;
  font-weight: 700;
  font-size: 15px;
  border-bottom: 2px solid #333;
  padding: 20px 0 10px;
  margin: 0;
  text-transform: uppercase;
}

input[type="text"] {
  margin: 0;
  font-size: 18px;
  line-height: 18px;
  height: 18px;
  padding: 10px;
  border: 1px solid #ddd;
  background: #fff;
  border-radius: 6px;
  font-family: Lato, sans-serif;
  color: #888;
}

input[type="text"]:focus {
  color: #333;
}

/* New Task */

label[for="new-task"] {
  display: block;
  margin: 0 0 20px;
}

input#new-task {
  float: left;
  width: 318px;
}

p > button:hover {
  color: #0fc57c;
}

/* Task list */

li {
  overflow: hidden;
  padding: 20px 0;
  border-bottom: 1px solid #eee;
}

li > input[type="checkbox"] {
  margin: 0 10px;
  position: relative;
  top: 15px;
}

li > label {
  font-size: 18px;
  line-height: 40px;
  width: 237px;
  padding: 0 0 0 11px;
}

li > input[type="text"] {
  width: 226px;
}

li > .delete:hover {
  color: #cf2323;
}

/* Completed */

#completed-tasks label {
  text-decoration: line-through;
  color: #888;
}

</style>
