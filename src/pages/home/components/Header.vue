<template>
    <div class='header'>
        <div class="header-left">
            <div class="icon-left"><i class="iconfont iconreturn"></i></div>
        </div>
        <div class="header-input">
            <i class="iconfont iconsearch"></i> 输入城市/景点/游玩主题</div>
        <div class="header-right">城市<i class="iconfont iconarrow"></i></div>
    </div>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style lang='stylus' scoped>
    @import '~styles/varibles.styl'
    .header 
        display: flex
        line-height: .86rem
        background: $bgColor
        color: #fff
        .header-left
            width: 0.64rem
            float: left
            .icon-left
                text-align: center
                font-size: .4rem
        .header-input
            flex:1
            border-radius: .1rem
            background: #ffffff
            color: #ccc
            height: .64rem
            line-height: .64rem
            margin-top: .12rem
            margin-left: .2rem
            padding-left: .1rem
        .header-right
            width: 1.24rem
            float:right
            text-align: center
            .iconarrow
                margin-left: 0.09rem
                font-size: .24rem
</style>

