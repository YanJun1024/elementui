<template>
  <el-container style="height: 100vh; border: 1px solid #eee">
    <el-aside style="width:200px ;min-height:100vh; background-color:#001529;">
      <div
        style="height: 60px;background-color: #8c939d;color:white;display: flex;align-items: center;justify-content: center;">
        logo
      </div>
      <el-menu style="border:none;" active-text-color="#fff" text-color="rgba(255,255,255,0.65)"
        background-color="#001529" :default-activer="$route.path" router>
        <el-menu-item index="/">
          <template>
            <i class="el-icon-house">
              <span>系统首页</span>
            </i>
          </template>
        </el-menu-item>
        <el-menu-item index="/element"> Element页面</el-menu-item>
        <el-menu-item>
          系统首页
        </el-menu-item>
        <el-menu-item>
          系统首页
        </el-menu-item>
        <el-submenu>
          <template slot="title">
            <i class="el-icon-menu">
              <span>系统首页</span>
            </i>
          </template>
          <el-menu-item>
            用户信息
          </el-menu-item>
        </el-submenu>
      </el-menu>
    </el-aside>

    <el-container>
      <el-header style="text-align: right; font-size: 12px">
        <el-dropdown>
          <i class="el-icon-setting" style="margin-right: 15px"></i>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>查看</el-dropdown-item>
            <el-dropdown-item>新增</el-dropdown-item>
            <el-dropdown-item>删除</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
        <span>王小虎</span>
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
    return {};
  },
};
</script>
<style>
html,
body {
  padding: 0;
  margin: 0;
}

.el-header {
  background-color: #b3c0d1;
  color: #333;
  line-height: 60px;
}

.el-aside {
  color: #333;
}

el-menu--inline el-menu-item {
  background-color: #000c17 !important;
}
</style>
