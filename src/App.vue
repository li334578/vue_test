<template>
  <div id="app">
    <!-- <MySchool v-on:wb="showSonParam" /> -->
    <MySchool ref="mysc"/>
    <hr />
    <MyStudent />
    <hr />
    <img alt="Vue logo" src="./assets/logo.png" />
  </div>
</template>

<script>
import MySchool from "./components/MySchool.vue";
import MyStudent from "./components/MyStudent.vue";

export default {
  name: "App",
  components: {
    MySchool,
    MyStudent,
  },
  methods:{
    showSonParam(value) {
      console.log('123',value)
    }
  },
  mounted(){
    // 手动绑定事件
    this.$refs.mysc.$on('wb',this.showSonParam);
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
