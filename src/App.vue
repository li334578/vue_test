<template>
  <!-- <div id="app"> -->
  <!-- <MyStudent2Vue :name="'张三'" :age="33" :sex="'男'"/> -->
  <!-- <MySchoolVue/> -->
  <!-- <hr/> -->
  <!-- <MyStudentVue/> -->
  <!-- <hr/> -->
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <!-- </div> -->

  <div id="app">
    <div class="todo-container">
      <div class="todo-wrap">
        <MyHeaderVue :addTodo="addTodo" />
        <MyListVue :todos="todos" />
        <MyFooterVue />
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import MySchoolVue from './components/MySchool.vue';
// import MyStudentVue from './components/MyStudent.vue';
// import MyStudent2Vue from "./components/MyStudent2.vue";
import MyHeaderVue from "./components/MyHeader.vue";
import MyListVue from "./components/MyList.vue";
import MyFooterVue from "./components/MyFooter.vue";

export default {
  name: "App",
  components: {
    MyHeaderVue,
    MyListVue,
    MyFooterVue,
  },
  data() {
    return {
      todos: [
        { id: "001", title: "抽烟", done: true },
        { id: "002", title: "喝酒", done: false },
        { id: "003", title: "烫头", done: true },
      ],
    };
  },
  methods: {
    addTodo(todo) {
      this.todos.unshift(todo)
    },
  },
};
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */

/*base*/
body {
  background: #fff;
}

.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2),
    0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn:focus {
  outline: none;
}

.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
</style>
