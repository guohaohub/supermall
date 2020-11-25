<template>
  <div id="app">
    <main-tabar/>
    <router-view/>
  </div>

</template>
<script>
  import MainTabar from 'components/content/maintabar/MainTabar'
 export default {
   name: 'app',
   components:{
     MainTabar
   }
 }
</script>

<style>
  @import "./assets/css/base.css";
</style>
