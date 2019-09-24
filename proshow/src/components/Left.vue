<template>
    <div>
        <div class="title">热门推荐</div>
        <ul class="menu">
            <li @click="menu1">笔记本电脑</li>
            <li @click="menu2">手机</li>
            <li>服饰</li>
            <li>手表</li>
            <li>书籍</li>
            <li>玩具</li>
            <li>小家电</li>
            <li>学习用品</li>
            <li>办公用品</li>
            <li>旅游必备</li>
            <li>游戏卡通</li>
        </ul>
    </div>
</template>
<style>
.title{
    width: 100px;
    color: red;
}
.menu li{
    list-style: none;
    height: 50px;
    margin-bottom: 2px;
    background-color: white;
    line-height: 50px;
    cursor: pointer;
}
</style>
<script>
import Msg from './msg.js'
export default{
    methods:{
        menu1:function(){
            Msg.$emit("val","1");
        },
        menu2:function(){
            Msg.$emit("val","2");
        }
    }
}
</script>