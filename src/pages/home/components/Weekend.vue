<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
        <div class="item-img-warrper">
          <img class="item-img" :src="item.imgUrl" alt>
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeWeekend",
  data() {
    return {
      recommendList: [
        {
          id: "0001",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1811/8a/e1edf5c1c52ff4.jpg_r_640x214_40693298.jpg",
          title: "当地人爱玩",
          desc: "朝辞白帝彩云间.....，重温诗仙李白的经典诗词，欣赏浓浓人文气息"
        },
        {
          id: "0002",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1811/65/7322301be0a92c.jpg_r_640x214_a3485c55.jpg",
          title: "摩崖石刻造像",
          desc:
            "诸事不顺，来抱佛脚，中国最壮观的大佛大盘点~来一场真正的“佛”系之旅，乐山大佛是首选"
        },
        {
          id: "0003",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1606/66/6d3cd39ae06500.jpg_r_640x214_f7c64cd2.jpg",
          title: "绵阳必游",
          desc: "伟大浪漫主义诗人李白的故乡"
        },
        {
          id: "0004",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1812/58/ebdb4ae5c789be.jpg_r_640x214_21321088.jpg",
          title: "欢乐亲子时光",
          desc: "带着孩子踏上旅途吧，增长知识，开阔眼界，边玩边学！"
        }
      ]
    };
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.title {
  line-height: 0.8rem;
  text-indent: 0.2rem;
  background: #eee;
}

.item-img-warrper {
  height: 0;
  overflow: hidden;
  padding-bottom: 37.9%;
}

.item-img {
  width: 100%;
}

.item-info {
  padding: 0.1rem;

  .item-title {
    line-height: 0.54rem;
    font-size: 0.32rem;
    ellipsis();
  }

  .item-desc {
    line-height: 0.4rem;
    color: #ccc;
    ellipsis();
  }
}
</style>
