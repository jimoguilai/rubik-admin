<template>
  <header class="ra-header">
    <div class="ra-header__hd">
      <a class="ra-brand ra-brand--lg" href="javascript:;">Rubik Admin</a>
      <a class="ra-brand ra-brand--sm" href="javascript:;">RA</a>
    </div>
    <div class="ra-header__bd">
      <!-- ra-header__menu left -->
      <el-menu class="ra-header__menu ra-header__menu--left" mode="horizontal">
        <el-menu-item v-if="!$store.state.asideTop" index="1" @click="$store.state.asideFold = !$store.state.asideFold">
          <svg class="icon-svg ra-header__icon-menu ra-header__icon-menu--rz180" aria-hidden="true"><use xlink:href="#icon-outdent"></use></svg>
        </el-menu-item>
      </el-menu>
      <!-- ra-header__menu right -->
      <el-menu class="ra-header__menu ra-header__menu--right" mode="horizontal">
        <el-menu-item index="2">
            <a href="#" target="_blank">
              <svg class="icon-svg ra-header__icon-menu" aria-hidden="true"><use xlink:href="#icon-earth"></use></svg>
            </a>
          </el-menu-item>
        <el-menu-item index="3">
          <svg class="icon-svg ra-header__icon-menu" aria-hidden="true"><use xlink:href="#icon-sync"></use></svg>
        </el-menu-item>
        <el-menu-item index="4">
          <svg class="icon-svg ra-header__icon-menu" aria-hidden="true"><use xlink:href="#icon-fullscreen"></use></svg>
        </el-menu-item>
        <el-menu-item index="1" @click="searchVisible = !searchVisible" class="ra-search__toggle">
          <svg class="icon-svg ra-header__icon-menu" aria-hidden="true"><use xlink:href="#icon-search"></use></svg>
        </el-menu-item>
        <el-submenu index="2" :popper-append-to-body="false" class="not-arrow t-center">
          <template slot="title">
            <el-button size="mini">简体中文</el-button>
          </template>
          <el-menu-item index="2-1">简体中文</el-menu-item>
          <el-menu-item index="2-2">繁體中文</el-menu-item>
          <el-menu-item index="2-3">English</el-menu-item>
        </el-submenu>
        <el-submenu index="3" :popper-append-to-body="false">
          <template slot="title">
            <img class="ra-avatar" src="@/assets/images/avatar.png">
            <span>admin</span>
          </template>
          <el-menu-item index="3-1">修改密码</el-menu-item>
          <el-menu-item index="3-2">退出</el-menu-item>
        </el-submenu>
        <el-menu-item index="1" @click="controlOpen = !controlOpen">
          <svg class="icon-svg ra-header__icon-menu" aria-hidden="true"><use xlink:href="#icon-setting"></use></svg>
        </el-menu-item>
      </el-menu>
      <!-- ra-search -->
      <div class="ra-search" :class="{ 'ra-search--show': searchVisible }">
        <div class="ra-search__inner">
          <el-input class="ra-search__input" v-model="search" placeholder="搜索关键字" clearable>
            <svg slot="prepend" class="icon-svg" aria-hidden="true"><use xlink:href="#icon-search"></use></svg>
          </el-input>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>
