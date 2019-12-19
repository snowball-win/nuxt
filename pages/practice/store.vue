<template>
  <section class="p-10">
    <h1> {{ value }} </h1>
    <h1> {{ result }} </h1>
    <el-button type="danger" @click="change">点击</el-button>
  </section>
</template>

<script>
  import { mapState, mapMutations, mapActions, mapGetters } from 'vuex';
export default {
  data() {
    return {
      result: false
    };
  },
  computed: {
    ...mapGetters('filter', [
      'include'
    ]),
    ...mapState({
      value: state => state.filter.value
    })
  },
  methods: {
    ...mapMutations('filter', [
      'SET_VALUE'
    ]),
    ...mapActions('filter', [
      'getInfo'
    ]),
    change() {
      this.result = !this.result
      // this.result = this.include(1);
      this.getInfo('你好');
      // this.SET_VALUE('HELLO YIYI');
    }
  },
  mounted() {
  },
  beforeDestroy() {
  }
};
</script>
// vuex实践，尝试普通的方法与模块映射的方法
// mapState, mapMutations, mapActions, mapGetters
// https://www.cnblogs.com/jin-zhe/p/9932011.html
// 1.在vue文件中，首先通过 import { mapState, mapMutations, mapActions, mapGetters } from 'vuex' 来引入我们需要的模块，按需引用，只需要引入本页面用到的模块即可
// 2. mapGetters和mapState需要在页面的计算属性computed中引入， mapMutations和mapActions需要在methods中引入，此时要注意模块的命名空间，如果vuex文件导出时标注了namespaced，我们使用时也需要写出才可以找到，反之则不需要
// 3.首先是mapState，使用mapState时，我有两种方法来取，两种方式都可以，这个方法是从store中取出这个变量，然后显示在此页面上，store变动的话，此页面也会跟着动态改变
// ...mapState({
//   value: state => state.filter.value
// })
// ...mapState('filter', {
//   value: state => state.value
// })
// 4.mapGetters类似于store的计算属性，我们可以通过mapGetters的方法在store里进行计算，然后返回我们需要的结果即可
// 上面例子就是点击按钮的时候传了一个数字到store里，然后判断store里的list是否包含这个数字，然后返回结果到页面，页面根据返回值重新刷新数据
// 5.MapMutation 是更改store中状态的唯一方法，Vuex 中的 mutation 非常类似于事件：每个 mutation 都有一个字符串的 事件类型 (type) 和 一个 回调函数 (handler)。这个回调函数就是我们实际进行状态更改的地方，并且它会接受 state 作为第一个参数
// 上面的例子是点击按钮时，直接通过mutation 的方法修改了store里的数据，然后把数据同步到页面
// 6.mapAction类似于mutation， 但是Action提交的是 mutation，而不是直接变更状态，Action可以包含任意异步操作，我们一般把异步获取数据的方法都放在这里，然后在回调函数里使用mutation里的方法把异步获取的数据保存在store里，然后把store里的数据传到页面
// 上面的例子是点击按钮时调用了action里的异步方法，然后在方法的回调函数里修改了store的数据，一般这里是把请求的结果进行保存，这里是省略了请求API方法
