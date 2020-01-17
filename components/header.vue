<template>
  <div class="header-wrapper">
    <!-- 使用element的layout组件布局 -->
    <el-row type="flex" class="header" justify="space-between">
      <!-- static文件里的内容可以直接引用 -->
      <!-- logo模块 -->
      <div class="logo"><img src="/logo.jpg" alt="" /></div>
      <!-- 导航栏部分 -->
      <div class="navs" type="flex">
        <nuxt-link to="/">首页</nuxt-link>
        <nuxt-link to="/post">旅游攻略</nuxt-link>
        <nuxt-link to="/hotel">酒店</nuxt-link>
        <nuxt-link to="/air">国内机票</nuxt-link>
      </div>
      <!-- 登录/注册 -->
      <div class="login" v-if="!$store.state.user.userInfo.token">
        <nuxt-link to="/user/login">登录/注册</nuxt-link>
      </div>
      <el-dropdown v-else>
        <span class="el-dropdown-link">
          <img
            :src="
              $axios.defaults.baseURL +
                $store.state.user.userInfo.user.defaultAvatar
            "
          />
          {{ $store.state.user.userInfo.user.nickname }}
          <i class="el-icon-arrow-down el-icon--right"></i>
        </span>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item>个人中心</el-dropdown-item>
          <el-dropdown-item>退出</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
    </el-row>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="less">
.el-dropdown-link {
  img {
    width: 36px;
    height: 36px;
    border-radius: 50px;
    vertical-align: middle;
  }
}
.header-wrapper {
  height: 60px;
  background: #fff;
  border-bottom: 1px #eee solid;
  box-shadow: 0 3px 2px #fefefd;
  min-width: 1000px;
  position: relative;
}
.header {
  width: 1000px;
  height: 60px;
  margin: 0 auto;
  img {
    display: block;
    width: 156px;
    height: 42px;
    margin-top: 9px;
  }
  .navs {
    flex: 1;
    margin-left: 20px;
  }
  .login {
    line-height: 60px;
    a {
      display: inline-block;
      height: 60px;
      box-sizing: border-box;
      padding: 0 15px;
      &:hover {
        color: #409eff;
      }
    }
  }
  .navs {
    line-height: 60px;
    a {
      display: inline-block;
      height: 60px;
      box-sizing: border-box;
      padding: 0 15px;
      &:hover {
        border-bottom: 5px #409eff solid;
        color: #409eff;
      }
    }
    .nuxt-link-exact-active {
      background: #409eff;
      color: #fff;

      &:hover {
        color: #fff;
      }
    }
  }
}
</style>
