<template>
  <h1>姓名: {{ name }}</h1>
  <h1>年龄: {{ age }}</h1>
  <h1>地址: {{ address.provinse }}-{{ address.city }}</h1>
  <button @click="changedUser">修改</button>
</template>

<script>
import { ref } from "vue";
export default {
  name: "App",
  setup() {
    let name = ref("张三");
    let age = ref("18");
    let address = ref({
      provinse: "山东",
      city: "济南",
    });

    function changedUser() {
      name.value = "李四";
      age.value = 20;
      address.value.provinse = "河北";
      address.value.city = "石家庄";
    }

    return { name, age, address, changedUser };
  },
};
</script>
