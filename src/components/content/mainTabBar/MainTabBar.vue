<template>
  <tab-bar>
        <!-- path="/home" :activeColor="txtColor" title="abc" :likes="a"  这里path="/home"因为是用字符串原封不动的传过去，所以没有必要用 : 号 ，如果是用变量的话，就需要用: -->
        <tab-bar-item path="/home" :activeColor="txtColor" title="abc" :likes="a">
          <img slot="item-icon" src="~assets/img/tabbar/home-icon.svg" alt="">
          <img slot="item-icon-active" src="~assets/img/tabbar/home-icon-active.svg" alt="">
          <div slot="item-text">首页</div>
        </tab-bar-item>
        <tab-bar-item path="/sort" :activeColor="txtColor" title="cde" :likes="b">
          <img slot="item-icon" src="~assets/img/tabbar/sort-icon.svg" alt="">
          <img slot="item-icon-active" src="~assets/img/tabbar/sort-icon-active.svg" alt="">
          <div slot="item-text">分类</div>
        </tab-bar-item>
        <tab-bar-item path="/cart" :activeColor="txtColor" title="fgk" :likes="c">
          <img slot="item-icon" src="~assets/img/tabbar/cart-icon.svg" alt="">
          <img slot="item-icon-active" src="~assets/img/tabbar/cart-icon-active.svg" alt="">
          <div slot="item-text">购物车</div>
        </tab-bar-item>
        <tab-bar-item path="/mine" :activeColor="txtColor" title="bbbb" :likes="d">
          <img slot="item-icon" src="~assets/img/tabbar/mine-icon.svg" alt="">
          <img slot="item-icon-active" src="~assets/img/tabbar/mine-icon-active.svg" alt="">
          <div slot="item-text">我的</div>
        </tab-bar-item>
    </tab-bar>
</template>

<script>
// 注意这里用得是路径引用起别名，上面图标地址也是
import TabBar from "componentsUrl/tabbar/TabBar"
import TabBarItem from "componentsUrl/tabbar/TabBarItem"

export default {
    name: "MainTabBar",
    components: {
        TabBar,
        TabBarItem
    },
    data () {
        return {
            a: 1233,
            b: 666,
            c: 888,
            d: 999,
            txtColor:"#f00"
        }
    }
}
</script>

<style>

</style>