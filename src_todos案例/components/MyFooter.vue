<template>
  <div class="todo-footer" v-show="allLength">
    <label>
      <!-- <input type="checkbox" :checked="checkAll" @change="myChangeChackAll" /> -->
      <input type="checkbox" v-model="checkAll" />
    </label>
    <span>
      <span>已完成{{ compeleteCount }}</span> / 全部 {{ todos.length }}
    </span>
    <button class="btn btn-danger" @click="myClearAll">清除已完成任务</button>
  </div>
</template>

<script>
export default {
  name: "MyFooter",
  props: ["todos", "changeChackAll","clearAll"],
  computed: {
    compeleteCount() {
      return this.todos.reduce((t, i) => {
        return i.done ? t + 1 : t;
      }, 0);
    },
    allLength() {
      return this.todos.length;
    },
    // checkAll() {
    //   return this.allLength == this.compeleteCount;
    // },
    checkAll: {
      set(value) {
        this.changeChackAll(value);
      },
      get() {
        return this.allLength == this.compeleteCount;
      },
    },
  },
  methods: {
    myChangeChackAll(e) {
      this.changeChackAll(e.target.checked);
    },
    myClearAll(){
      this.clearAll();
    }
  },
};
</script>

<style scoped>
/*footer*/
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}
</style>