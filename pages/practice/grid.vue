<template>
  <div>
    <div class="first">
      <div>一 gird</div>
      <div class="wrapper">
          <div class="item">1</div>
          <div class="item">2</div>
          <div class="item">3</div>
      </div>
    </div>
    <div class="second">
      <div>二 inline-gird</div>
      <span>foo</span>
      <div class="wrapper">
          <div class="item">1</div>
          <div class="item">2</div>
          <div class="item">3</div>
      </div>
      <span>bar</span>
    </div>
    <div class="third">
      <div>三 repeat</div>
       <div class="wrapper">
        <div class="item item-1">1</div>
        <div class="item item-2">2</div>
        <div class="item item-3">3</div>
        <div class="item item-4">4</div>
        <div class="item item-5">5</div>
        <div class="item item-6">6</div>
        <div class="item item-7">7</div>
        <div class="item item-8">8</div>
        <div class="item item-9">9</div>
      </div>
    </div>
    <div class="fourth">
      <div>四 fr</div>
      <div class="wrapper">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div> 
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style scoped lang="scss">
.first .wrapper,.second .wrapper{
  width:450px;
  background: #f3f3f3;
  text-align:center;
  display: grid;
  grid-template-columns: 150px 150px 150px;//用来指定行的宽度
  grid-template-rows: 150px 150px 150px;//用来指定行的宽度
  >.item{
    border: 1px solid red;
    &:first-of-type{
      background:#ef342a;
    }
    &:nth-of-type(2){
      background:#00a0a0;
    }
    &:nth-of-type(3){
      background:#a0a0ff;
    }
  }
}
.second{
  .wrapper{
    display: inline-grid;
  }
}
.third{
  .wrapper{
    display: grid;
    grid-template-columns: repeat(2, 100px 20px 80px);
    grid-template-rows: repeat(3, 100px);
    .item{
      font-size: 4em;
      text-align: center;
      border: 1px solid #e5e4e9;
    }
    .item-1 {
      background-color: #ef342a;
    }
    .item-2 {
      background-color: #f68f26;
    }
    .item-3 {
      background-color: #4ba946;
    }
    .item-4 {
      background-color: #0376c2;
    }
    .item-5 {
      background-color: #c077af;
    }
    .item-6 {
      background-color: #f8d29d;
    }
    .item-7 {
      background-color: #b5a87f;
    }
    .item-8 {
      background-color: #d0e4a9;
    }
    .item-9 {
      background-color: #4dc7ec;
    }
  }
}
.fourth{
  .wrapper{
      width:450px;
      background: #f3f3f3;
      text-align:center;
      display:grid;
      grid-template-columns: 1fr 2fr 1fr;
      grid-template-rows: 150px 150px 150px;
      >.item{
        border: 1px solid red;
        &:first-of-type{
          background:#ef342a;
        }
        &:nth-of-type(2){
          background:#00a0a0;
        }
        &:nth-of-type(3){
          background:#a0a0ff;
        }
      }
  }
}
</style>
// grid布局
// Grid 布局与 Flex 布局有一定的相似性，都可以指定容器内部多个项目的位置。但是，它们也存在重大区别。
// Flex 布局是轴线布局，只能指定"项目"针对轴线的位置，可以看作是一维布局。Grid 布局则是将容器划分成"行"和"列"，产生单元格，然后指定"项目所在"的单元格，可以看作是二维布局。Grid 布局远比 Flex 布局强大。
// http://www.ruanyifeng.com/blog/2019/03/grid-layout-tutorial.html
// https://www.cnblogs.com/cythia/p/10894598.html

// 本页面是本项目首次使用scss
// 1，安装依赖
// sudo npm i node-sass sass-loader scss-loader --save-dev
// 2，在nuxt.config.js文件css处加：
// { src: '~/assets/scss/global.scss', lang: 'sass' }
// 3，在使用的页面
// <style scoped lang="scss">