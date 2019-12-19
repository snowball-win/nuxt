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