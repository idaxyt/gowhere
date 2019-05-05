<template>
    <ul class="list">
        <li class='item'>A</li>
        <li class='item'>A</li>
        <li class='item'>A</li>
        <li class='item'>A</li>
        <li class='item'>A</li>
        <li class='item'>A</li>
    </ul>
</template>

<script>
export default {
    name: 'Alphabet'
}
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl'
.list
    // 垂直方向上居中
    display: flex;
    flex-direction: column;
    justify-content: center;
    // 垂直方向上居中    
    position: absolute;
    top: 1.58rem;
    right:0;
    bottom:0;
    width: .4rem;
    .item
        line-height: .4rem;
        color: $bgColor;
        text-align: center;
</style>
