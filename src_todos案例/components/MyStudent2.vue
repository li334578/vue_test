<template>
  <div>
    <h1>{{ msg }}</h1>
    <h2>学生姓名：{{ name }}</h2>
    <h2>学生年龄：{{ age }}</h2>
    <h2>学生年龄：{{ sex }}</h2>
  </div>
</template>

<script>
export default {
  name: "MyStudent2",
  data() {
    console.log(this)
    return {
      msg:'我是学生'
    };
  },
  // props:['name','age','sex']
  props:{
    name:String,
    age:Number,
    sex:String
  }
};
</script>