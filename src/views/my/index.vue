<template>
  <div class="layout">
    <NavBar></NavBar>
    <div class="layout-right">
      <HeaderView></HeaderView>
      <div class="content">
        <div class="top"></div>
      </div>
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import NavBar  from '../layout/NavBar.vue'
import HeaderView from '../layout/HeaderView.vue'
export default {
  name:'app',
  data(){
    return {}
  },
  components: {
    NavBar,
    HeaderView
  }
}
</script>

<style lang="less" scoped> 
  .layout{
    width: 100%;
    height: 100%;
    display: flex;
    .layout-right{
      flex:1
    }
    .top {
      height: 300px;
      background-color: red;
    }
  }
</style>