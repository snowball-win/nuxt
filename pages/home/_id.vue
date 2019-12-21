<template>
  <div class="container">
    <div>
      <!-- <logo /> -->
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
export default {
  components: {
    Logo
  },
  data(){
    return {
      name: 'yiyi'
    }
  },
  computed:{
  },
  methods:{
  },
  mounted(){
    console.log('st',this._routerRoot._route.params.id)
  }
}
</script>

<style>
</style>
// 在Nuxt.js里面定义带参数的动态路由，需要创建对应的以下划线作为前缀的Vue文件或目录