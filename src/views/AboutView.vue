<template>
  <table border="1">
    <thead>
    <tr>
      <th>ID</th>
      <th>标题</th>
    </tr>
    </thead>
    <tbody>
    <tr v-for="item in data_list">
      <td>{{ item.id }}</td>
      <td>{{ item.name }}</td>
    </tr>
    </tbody>
  </table>
</template>

<script setup>
import {onMounted, ref} from "vue";
import axios from "axios";

const data_list = ref([])
onMounted(function (){
  //使用axios发送请求
  axios({
    method: "get",
    url: "https://api.luffycity.com/api/v1/course/category/actual/?courseType=actual",
    headers: {
      "Content-Type": "application/json"
    }
  }).then(function (res) {
    data_list.value = res.data.data

  }).catch(function (error) {
    console.log("请求失败", error);
  })
})
</script>

<style scoped>
</style>
