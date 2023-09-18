<template>
  <el-container style="height: 100vh; border: 1px solid #eee">
    <el-aside :width="asideWidth" style="min-height:100vh; background-color:#001529;">
      <div
        style="height: 60px;background-color: #000c17;color:white;display: flex;align-items: center;justify-content: center;">
        <img src="@/assets/logo.png" alt="" style="width: 40px;height: 40px;">
        <span class="logo-title" v-show="!isCollapse">Vue-Admin</span>
      </div>
      <el-menu :collapse="isCollapse" :collapse-transition="false" style="border:none;" active-text-color="#fff"
        text-color="rgba(255,255,255,0.65)" background-color="#001529" :default-activer="$route.path" router>
        <el-menu-item index="/">
          <template>
            <i class="el-icon-house">
              <span>系统首页</span>
            </i>
          </template>
        </el-menu-item>
        <el-menu-item index="/element">
          <template>
            <i class="el-icon-house">
              <span>系统首页</span>
            </i>
          </template>
        </el-menu-item>
        <el-menu-item index="/2">
          <template>
            <i class="el-icon-house">
              <span>系统首页</span>
            </i>
          </template>
        </el-menu-item>

        <el-submenu index="/submenu">
          <template slot="title">
            <i class="el-icon-menu">
              <span>系统首页</span>
            </i>
          </template>
          <el-menu-item index="/submenu">
            用户信息
          </el-menu-item>
          <el-menu-item index="/submenu2">
            管理员信息
          </el-menu-item>
        </el-submenu>
      </el-menu>
    </el-aside>

    <el-container>
      <el-header style="text-align: right; font-size: 12px">
        <i :class="collapseIcon" style="width:26px;font-size: 36px;" @click="handleCollapse"></i>
        <el-breadcrumb separator-class="el-icon-arrow-right" style="margin-left: 20px;">
          <!-- <el-breadcrumb-item :to="{ path: '/submenu2' }">首页</el-breadcrumb-item> -->
          <el-breadcrumb-item :to="{ path: '/1' }"><a href="/">活动管理</a></el-breadcrumb-item>
          <el-breadcrumb-item :to="{ path: '/element' }"><a href="/">活动管理</a></el-breadcrumb-item>
        </el-breadcrumb>
        <div style="flex:1;width: 0;display: flex;align-items: center;justify-content: flex-end;">
          <el-dropdown placement="bottom">

            <div style="display: flex;align-items: center; cursor:default">
              <img src="@/assets/logo.png" alt="" style="width: 40px;height: 40px;">
              <span>游客</span>

            </div>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>个人信息</el-dropdown-item>
              <el-dropdown-item>修改密码</el-dropdown-item>
              <el-dropdown-item>退出登录</el-dropdown-item>

            </el-dropdown-menu>
          </el-dropdown>
        </div>
      </el-header>

      <el-main>
        <router-view></router-view>
      </el-main>
    </el-container>
  </el-container>
</template>
<script>
export default {
  data() {
    return {
      isCollapse: false,
      asideWidth: "200px",
      collapseIcon: "el-icon-s-fold",

    };//不收缩
  },
  methods: {
    handleCollapse() {
      this.isCollapse = !this.isCollapse;
      this.asideWidth = this.isCollapse ? "64px" : "200px";
      this.collapseIcon = this.isCollapse ? "el-icon-s-unfold" : "el-icon-s-fold";
    },
  },

};

</script>
<style>
html,
body {
  padding: 0;
  margin: 0;
}

/* .el-header {
  background-color: #b3c0d1;
  color: #333;
  line-height: 60px;
} */

.el-aside {
  color: #333;
}

.el-menu--inline .el-menu-item {
  background-color: #000c17 !important;
}

.el-menu-item:hover,
.el-submenu__title:hover {
  color: #fff !important;
}

.el-submenu__title:hover i {
  color: #fff !important;
}

.el-menu-item:hover i {
  color: #fff !important;

}

.el-menu-item.is-active {
  background-color: #1890ff !important;
  border-radius: 5px !important;
  margin: 4px !important;
}

.el-submenu__title.is-opened {
  background-color: #1890ff !important;
  border-radius: 5px !important;
  margin: 4px !important;
}

.el-menu-item {
  height: 40px !important;
  line-height: 40px !important;
  margin: 4px !important;
}

.el-submenu__title {
  height: 40px !important;
  line-height: 40px !important;
  margin: 4px !important;
}

.el-submenu .el-menu-item {
  height: 40px !important;
  line-height: 40px !important;
  margin: 4px !important;
}

.el-submenu .el-menu-item.is-active {
  height: 50px;
  line-height: 50px;
  padding: 0 45px;
  min-width: 24px;
}

.el-aside {
  transition: width .2s;
  box-shadow: 2px 0 6px rgba(0, 21, 41, .35);
}

logo-title {
  margin-left: 10px;
  font-size: 20px;
  transition: all 0.2s;
}

.el-header {
  /* background-color: #000c17; */
  color: #333;
  text-align: center;
  line-height: 60px;
  box-shadow: 2px 0 6px rgba(0, 21, 41, .35);
  display: flex;
  align-items: center;
}
</style>
