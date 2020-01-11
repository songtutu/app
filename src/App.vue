<template>
  <div class="content">
    <!-- 顶部 header -->
    <mt-header fixed title="云委托"></mt-header>
    <!-- 中部 路由 router-view -->
    <router-view/>
    <!-- 底部 tabbar -->
    <nav class="mui-bar mui-bar-tab">
      <router-link to="/home" class="mui-tab-item mui-active">
        <span class="mui-icon mui-icon-home"></span>
        <span class="mui-tab-label">首页</span>
      </router-link>
      <a href="#" class="mui-tab-item">
        <span class="mui-icon mui-icon-contact"></span>
        <span class="mui-tab-label">会员</span>
      </a>
      <a href="#" class="mui-tab-item">
        <span class="mui-icon mui-icon-extra mui-icon-extra-cart">
        <span class="mui-badge">9</span></span>
        <span class="mui-tab-label">购物车</span>
      </a>
      <a href="#" class="mui-tab-item">
        <span class="mui-icon mui-icon-search"></span>
        <span class="mui-tab-label">搜索</span>
      </a>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'App',
  created () {
  }
}
</script>

<style>
.content{
  padding-top: 40px;
  padding-bottom: 50.4px;
}
</style>
