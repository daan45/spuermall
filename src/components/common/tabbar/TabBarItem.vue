<template>
    <div class="tab-bar-item" @click="itemClick">
        <div v-if="!isActive"><slot name="item-icon"></slot></div>
        <div v-else><slot name="item-icon-active"></slot></div>
        <!-- <div v-bind:class="{active: isActive}"><slot name="item-text"></slot></div> -->
        <!-- <div v-bind:style="isActive ? {color: this.activeColor} : {}"><slot name="item-text"></slot></div> -->
        <div v-bind:style="activeStyle"><slot name="item-text"></slot></div>
    </div>
</template>

<script>
export default {
    name: "TabBarItem",
    props: {
        path: String,
        title: String,
        likes: Number,
        activeColor: {
            type: String,
            default: "blue"
        }
    },
    data() {
        return {
         // isActive: true
        }
    },
    computed: {
        isActive() {
            return this.$route.path.indexOf(this.path) !== -1
            // !== 不等于-1，所以返回true
            // $toute.path表示当前活跃页面路由，indexOf(this.path)判断路径里面有没有跟我当前活跃页面路由匹配，这里this.path路径是App.vue页面通过点击传过来的path="/home"值。
        },
        activeStyle() {
            return this.isActive ? {color: this.activeColor} : {}
        }
    },
    methods: {
        itemClick() {
            this.$router.replace(this.path)   // 不想返回用replace  想返回用push
            console.log("this.path " + this.path);
            console.log("this.title " + this.title);
            console.log("this.likes " + this.likes);

            // console.log("this.iBoolean " + this.iBoolean);
            // console.log("this.nBool " + this.nBool);
            console.log(this.activeColor);
        }
    }
}
</script>

<style>
    .tab-bar-item {
        flex: 1;
        text-align: center;
        font-size:14px;
    }
    .tab-bar-item img {
        width:24px;
        height:24px;
        margin-top: 3px;
        vertical-align: middle;
        margin-bottom:2px;
    }
    /* .active {
        color:red;
    } */
</style>