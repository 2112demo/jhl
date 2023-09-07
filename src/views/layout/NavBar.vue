<template>
  <div class="navbar" :class="{ isColl: isCollapse }">
    <div class="top" :class="{ isColl: isCollapse }">
      <img src="../../assets/logo.png" alt="" width="32px">
      <span v-show="!isCollapse">灵活用工</span>
    </div>
    <div class="sye">
      <p>常用操作</p>
      <div class="iconFint">
        <el-menu :collapse="isCollapse" :collapse-transition="false">
          <!-- collapse="true"控制折叠 -->
          <el-submenu index="1">
            <template slot="title">
             <router-link to="/">
              <i class="el-icon-location"></i>
              <span v-show="!isCollapse">首页</span>
             </router-link>
            </template>
          </el-submenu>
        </el-menu>
      </div>
    </div>
    <div class="ywu">
      <p>业务管理</p>
      <el-menu
        default-active="2"
        class="el-menu-vertical-demo"
        @open="handleOpen"
        @close="handleClose"
        background-color="#fff"
        text-color="#000"
        active-text-color="#ffd04b"
        unique-opened="true"
        :collapse="isCollapse"
        :collapse-transition="false"
      >
        <!-- collapse="true"控制折叠 -->
        <el-submenu index="1">
          <template slot="title">
            <i class="el-icon-location"></i>
            <span>项目任务</span>
          </template>
          <el-menu-item-group>
           <router-link to="/my">
            <el-menu-item index="1-1" :router="true">批量新建订单</el-menu-item>
           </router-link>
            <el-menu-item index="1-2">项目列表</el-menu-item>
            <el-menu-item index="1-3">任务派单</el-menu-item>
            <el-menu-item index="1-4">订单列表</el-menu-item>
          </el-menu-item-group>
        </el-submenu>
        <el-submenu index="2">
          <template slot="title">
            <i class="el-icon-location"></i>
            <span>资金发票</span>
          </template>
          <el-menu-item-group>
            <el-menu-item index="2-1">批量新建订单</el-menu-item>
            <el-menu-item index="2-2">项目列表</el-menu-item>
            <el-menu-item index="2-3">任务派单</el-menu-item>
          </el-menu-item-group>
        </el-submenu>
        <el-submenu index="3">
          <template slot="title">
            <i class="el-icon-location"></i>
            <span>企业管理</span>
          </template>
          <el-menu-item-group>
            <el-menu-item index="3-1">批量新建订单</el-menu-item>
          </el-menu-item-group>
        </el-submenu>
      </el-menu>
    </div>
    <div class="fwzx">
      <p>服务中心</p>
      <el-menu
        default-active="2"
        class="el-menu-vertical-demo"
        @open="handleOpen"
        @close="handleClose"
        background-color="#fff"
        text-color="#000"
        active-text-color="#ffd04b"
        unique-opened="true"
        :collapse="isCollapse"
        :collapse-transition="false"
      >
        <!-- collapse="true"控制折叠 -->
        <el-submenu index="4">
          <template slot="title">
            <i class="el-icon-location"></i>
            <span>服务中心&安全</span>
          </template>
          <el-menu-item-group>
            <el-menu-item index="4-1">批量新建订单</el-menu-item>
          </el-menu-item-group>
        </el-submenu>
      </el-menu>
    </div>
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
  name: "NavBar",
  data() {
    return {
     
    };
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
  },
  computed: {
    ...mapState({
      isCollapse: (state) => state.navCollapse.isCollapse,
    }),
  },
};
</script>

<style lang="less" scoped>
.navbar {
  width: 220px;
  height: 100vh;
  position: relative;
  // color: red;
  background-color: white;
  transition: all .3s;
  &.isColl {
    width: 80px;
  }
  .top {
    width: 220px;
    height: 40px;
    background-color: red;
    color: white;
    text-align: center;
    line-height: 40px;
    img {
      vertical-align: middle;
    }
    span {
      min-width: 80px;
      color: white;
      font-weight: bold;
      display: inline-block;

    }
    &.isColl {
      width: 80px;
    }
  }
  .sye > p {
    margin-top: 10px;
    margin-left: 5px;
    color: #ccc;
    font-weight: 700;
    font-size: 13px;
  }
  .com1 {
    margin-left: 25px;
    margin-top: 20px;
    i {
      font-size: 25px;
    }
    button {
      color: black;
      margin-left: 15px;
    }
  }
}
</style>