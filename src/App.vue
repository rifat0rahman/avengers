<template>
  <div>
    <navbar></navbar>
    <router-view></router-view>
    
  </div>
</template>


<style>
</style>


<script>
import navbar from './components/navbar.vue'
export default {
  components:{
    navbar
  }
}
</script>


