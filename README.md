# uichuan47

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```



## dev_notes

### 1.通过vue-router传递参数

```js
// 通过url传递参数
import {useRoute,onBeforeRouteUpdate} from "vue-router";
const route = useRoute()
console.log(route.query)
//通过onBeforeRouteUpdate记录from，to
onBeforeRouteUpdate(function (to,from)
{
  console.log(from,to)
})
```



### 2.通过axios发送请求

```js
<script setup>
import axios from "axios";
// 通过axios发送get请求，获取数据
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
```

