<template>
  <div>
    <el-menu
      :default-active="currentPath"
      router
      mode="horizontal"
      @select="handleSelect"
      background-color="white"
      text-color="#222"
      active-text-color="red"
      style="min-width: 1300px">
      <el-menu-item v-for="(item,i) in navList" :key="i" :index="item.name">
        {{ item.navItem }}
      </el-menu-item>
      <!--<i class="el-icon-switch-button" v-on:click="logout" style="float:right;font-size: 40px;color: #222;padding: 10px"></i>-->
      <span style="position: absolute;padding-top: 20px;right: 43%;font-size: 20px;font-weight: bold">Library System</span>
    </el-menu>
  </div>
</template>

<script>
export default {
  name: 'NavMenu',
  data () {
    return {
      // currentPath: this.$route.path,
      navList: [
        {name: '/index', navItem: '首页'},
        {name: '/library', navItem: '图书馆'}
      ],
      keywords: ''
    }
  },
  computed: {
    currentPath () {
      return this.$route.path
    }
  },
  methods: {
    handleSelect (key, keyPath) {
      console.log(key)
      console.log('...')
      console.log(keyPath)
    }
  }
}
</script>

<style scoped>
  a{
    text-decoration: none;
  }

  span {
    pointer-events: none;
  }

  .el-icon-switch-button {
    cursor: pointer;
    /*去除点击时的框线*/
    outline:0;
  }
</style>
