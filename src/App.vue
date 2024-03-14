<script setup>
</script>

<template>
  <div class="menu">
    <div style="padding-left: 40px;">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about?v1=123">About1</RouterLink>
      <RouterLink :to="{name:'about',query:{v2:456}}">About2</RouterLink>
    </div>
  </div>
  <div class="container">
    <RouterView />
  </div>
  
</template>

<style>
.body{
  margin: 0;
}
.menu{
  height: 48px;
  line-height: 48px;
  background-color: #499ef3;
}

.container{
  width: 980px;
  margin: 0 auto;
}

.menu a{
  display: inline-block;
  color: white;
  text-decoration: none;
  padding: 0 10px;
}
</style>
