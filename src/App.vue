<template>
  <h1>姓名: {{ name }}</h1>
  <h1>年龄: {{ age }}</h1>
  <h1>地址: {{ address.provinse }}-{{ address.city }}</h1>
  <h1>爱好: {{ hobby }}</h1>
  <button @click="changedUser">修改</button>
</template>

<script>
import { ref, reactive } from "vue";
export default {
  name: "App",
  setup() {
    let name = ref("张三");
    let age = ref("18");
    let address = reactive({
      provinse: "山东",
      city: "济南",
    });
    let hobby = reactive(["篮球", "足球", "羽毛球"]);

    function changedUser() {
      name.value = "李四";
      age.value = 20;
      address.provinse = "河北";
      address.city = "石家庄";
      hobby[2] = "乒乓球";
    }

    return { name, age, address, hobby, changedUser };
  },
};
</script>
