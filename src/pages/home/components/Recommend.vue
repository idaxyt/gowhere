<template>
  <div>
    <div class="title">猜你喜欢</div>
    <ul>
      <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" alt>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  data() {
    return {
      recommendList: [
        {
          id: "0001",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1806/9a/9a9771437d0e23c7a3.img.jpg_200x200_0e469ab9.jpg",
          title: "百年好合爱情谷",
          desc: "771条评论"
        },
        {
          id: "0002",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1705/e1/e176b025687ef3bda3.water.jpg_200x200_dbd595fb.jpg",
          title: "梦幻岛欢动世界",
          desc: "17条评论"
        },
        {
          id: "0003",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1904/e7/e7c19ba5d4f2c742a3.water.jpg_200x200_150dc6d9.jpg",
          title: "九皇山",
          desc: "2453条评论"
        },
        {
          id: "0004",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1801/34/34b0ceadcc9647e3a3.img.jpg_200x200_0c578b0d.jpg",
          title: "中华洞天",
          desc: "885条评论"
        },
        {
          id: "0005",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1505/33/332724a457637e60.water.jpg_200x200_efc3c5b0.jpg",
          title: "绵州温泉酒店",
          desc: "324条评论"
        },
        {
          id: "0006",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/201408/13/e2f90b64bfe9fad7083020263b68266e.jpg_200x200_40d98c1c.jpg",
          title: "绵阳罗浮山会议中心",
          desc: "224条评论"
        },
        {
          id: "0007",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1502/e0/e055cb2c79da8f33.water.jpg_200x200_93193a93.jpg",
          title: "药王谷",
          desc: "1647条评论"
        },
        {
          id: "0008",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/201407/17/a272ac452d39b286b1275ad32361632a.jpg_200x200_c02cff43.jpg",
          title: "七曲山大庙",
          desc: "1999条评论"
        },
        {
          id: "0009",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/201405/08/fb5315728846b44709a7b648f4fa5e98.jpg_200x200_2eeee62b.jpg",
          title: "越王楼",
          desc: "361条评论"
        }
      ]
    };
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.title {
  margin-top: 0.2rem;
  line-height: 0.8rem;
  text-indent: 0.2rem;
  background: #eee;
}

.item {
  display: flex;
  height: 2.4rem;
  overflow: hidden;
}

.item-img {
  width: 2.2rem;
  height: 2.2rem;
  padding: 0.1rem;
}

.item-info {
  flex: 1;
  padding: 0.1rem;
  min-width: 0;

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

  .item-button {
    line-height: 0.44rem;
    margin-top: 0.16rem;
    background: #ff9300;
    padding: 0 0.2rem;
    border-raduis: 0.06rem;
    color: #fff;
  }
}
</style>
