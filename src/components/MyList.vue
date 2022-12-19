<template>
  <ul class="todo-main">
    <MyItemVue v-for="todoObj in todos" :todo="todoObj" :key="todoObj.id"/>
  </ul>
</template>

<script>
import MyItemVue from "./MyItem.vue";
export default {
  name: "MyList",
  components: {
    MyItemVue,
  },
  props:['todos']
};
</script>

<style scoped>

/*main*/
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>