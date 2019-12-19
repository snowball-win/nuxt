<template>
  <div class="container">
    <div>
      <!-- <logo /> -->
      <div>
        <el-button>123</el-button>
        <input type="text" class="test">
        <p @click="changeName">change{{name}}</p>
        <p>reverse{{reversedNames}}</p>
      </div>
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
    reversedNames(){
      return this.name.split('').reverse().join('')
    }
  },
  methods:{
    testDefineProperty(){
      var txt = document.querySelector('.test')
      var person = {
          name: 'jack'
      }
      let _this = this
      txt.onchange = function () {
        person.name = this.value
        console.log(person.name)
      }
      Object.defineProperty(person, 'name', {
        get: function () { //当要执行person.name时触发get方法
            //这里需要一个返回值,不然console.log(person.name)就会是undefined
            console.log('get',this)
            return txt.value //返回input的内容
        },
        set: function (newValue) {//当person.name发生改变时触发
            //将改变的值赋给input
            console.log('set',this,newValue)
            _this.name = newValue
            txt.value = newValue
        }
      })
    },
    changeName(){
      var txt = document.querySelector('.test')
      txt.value = 'xingmou'
      this.testDefineProperty()
    }
  },
  mounted(){
    this.testDefineProperty()
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
