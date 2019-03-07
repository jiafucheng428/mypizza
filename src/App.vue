<template>
  <div id="app" class="container">
    <Header></Header>
  <router-view/>

  <router-view name="history">  </router-view>
  <router-view name="history">  </router-view>
  </div>
</template>

<script>
import Header from '@/components/Header'
export default {
  name: 'App',
  data(){
    return{
      img:'../static/logo.png'
    }
  },
  components:{
    'Header':Header
  }
}
</script>

<style>

</style>
