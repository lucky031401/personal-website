<template>
  <main>
    <h1>Home page</h1>
    <div id="app" class="static" v-bind:class="{ active: isActive }" style="width:200px;height:200px">hi vue</div>
  </main>
</template>
<script>
  export default{
      data(){
        return{
          isActive:true
        }
      }
  }
</script>

<style>
.active{background: skyblue;}
</style>
