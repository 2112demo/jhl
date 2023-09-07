<template>
  <div class="header">
    <el-button
      @click="changeShow"
      icon="el-icon-s-fold"
      v-show="!isShow"
    ></el-button>
    <el-button
      @click="changeShow"
      icon="el-icon-s-unfold"
      v-show="isShow"
    ></el-button>
  </div>
</template>

<script>
import {mapMutations} from "vuex"
export default {
  name: "HeaderView",
  data() {
    return {
      isShow: true,
    };
  },
  methods:{
    ...mapMutations({
      changeIsCollapse:"navCollapse/changeIsCollapse"
    }),
    changeShow(){
      this.isShow = !this.isShow
      this.changeIsCollapse()
    }
  }
};
</script>

<style lang="less" scoped>
.header {
  height: 40px;
  background-color: blue;
  box-shadow: 0px 5px 5px #eee;
  // padding-left: 20px;
  button {
    width: 35px;
    height: 35px;
    margin: 0;
    font-size: 25px;
    padding: 7px 15px;
    border: none;
    background-color: blue;
    color: #fff;
  }
}
</style>