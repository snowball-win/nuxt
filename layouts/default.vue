<template>
  <div>
    <el-menu
      :default-active="activeIndex2"
      class="el-menu-demo"
      mode="horizontal"
      @select="handleSelect"
      background-color="#545c64"
      text-color="#fff"
      active-text-color="#ffd04b"
    >
      <el-menu-item index="1">HTML</el-menu-item>
      <el-submenu index="2">
        <template slot="title">CSS</template>
        <el-menu-item index="2-1">选项1</el-menu-item>
        <el-menu-item index="2-2">选项2</el-menu-item>
        <el-menu-item index="2-3">选项3</el-menu-item>
      </el-submenu>
      <el-menu-item index="3">JavaScript</el-menu-item>
      <el-menu-item index="4">JQuery</el-menu-item>
      <el-menu-item index="5">Vue</el-menu-item>
      <el-menu-item index="6">Nuxt</el-menu-item>
      <el-menu-item index="7">Node</el-menu-item>
      <el-menu-item index="8">MySql</el-menu-item>
      <el-menu-item index="9">Git</el-menu-item>
      <el-menu-item index="10"><a
          href="http://blog.poetries.top/FE-Interview-Questions/"
          target="_blank"
        >interview</a></el-menu-item>
      <el-submenu index="11">
        <template slot="title">项目</template>
        <!-- <el-menu-item index="10-1">党媒头条</el-menu-item>
        <el-menu-item index="10-2">随心游</el-menu-item> -->
        <el-menu-item index="11-1">
          <a
            href="https://www.haolvshi.com.cn/"
            target="_blank"
          >好律师</a></el-menu-item>
        <el-menu-item index="11-2">
          <a
            href="https://www.sitechdev.com/"
            target="_blank"
          >新特汽车</a></el-menu-item>
      </el-submenu>
      <el-submenu index="12">
        <template slot="title">博客/网站</template>
        <el-menu-item index="12-1">
          <a
            href="https://segmentfault.com/"
            target="_blank"
          >segmentFault</a></el-menu-item>
      </el-submenu>
      <el-menu-item index="13">开发环境</el-menu-item>
      <el-menu-item index="14">生活</el-menu-item>
    </el-menu>
    <nuxt />
  </div>
</template>
<script>
export default {
  data () {
    return {
      activeIndex2: '1'
    }
  },
  methods: {
    handleSelect (key, keyPath) {
      console.log(key, keyPath)
    }
  },
  mounted () {

  }
}
</script>
<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
