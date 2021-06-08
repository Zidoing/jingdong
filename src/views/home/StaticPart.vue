<template>
  <div class="position">
    <span class="iconfont position__icon">&#xe64f;</span>
    北京理工大学国防科技园2号楼2222222222222222222222222222222222222222222
    <span class="iconfont position_notice">&#xe649;</span>
  </div>
  <div class="search">
    <span class="iconfont search__icon">&#xe725;</span>
    山姆会员商店优惠商品
  </div>
  <div class="banner">
    <img class="banner__img" src="http://www.dell-lee.com/imgs/vue3/banner.jpg" alt="">
  </div>
  <div class="icons">
    <div class="icons__item">
      <img class="icons__item__img" src="http://www.dell-lee.com/imgs/vue3/超市.png" alt="">
      <p class="icons__item__desc">超市便利</p>
    </div>
    <div class="icons__item">
      <img class="icons__item__img" src="http://www.dell-lee.com/imgs/vue3/菜市场.png" alt="">
      <p class="icons__item__desc">菜市场</p>
    </div>
    <div class="icons__item">
      <img class="icons__item__img" src="http://www.dell-lee.com/imgs/vue3/水果店.png" alt="">
      <p class="icons__item__desc">水果店</p>
    </div>
    <div class="icons__item">
      <img class="icons__item__img" src="http://www.dell-lee.com/imgs/vue3/鲜花.png" alt="">
      <p class="icons__item__desc">鲜花绿植</p>
    </div>
    <div class="icons__item">
      <img class="icons__item__img" src="http://www.dell-lee.com/imgs/vue3/医药健康.png" alt="">
      <p class="icons__item__desc">医药健康</p>
    </div>
    <div class="icons__item">
      <img class="icons__item__img" src="http://www.dell-lee.com/imgs/vue3/家居.png" alt="">
      <p class="icons__item__desc">家居时尚</p>
    </div>
    <div class="icons__item">
      <img class="icons__item__img" src="http://www.dell-lee.com/imgs/vue3/蛋糕.png" alt="">
      <p class="icons__item__desc">烘焙蛋糕</p>
    </div>
    <div class="icons__item">
      <img class="icons__item__img" src="http://www.dell-lee.com/imgs/vue3/签到.png" alt="">
      <p class="icons__item__desc">签到</p>
    </div>
    <div class="icons__item">
      <img class="icons__item__img" src="http://www.dell-lee.com/imgs/vue3/大牌免运.png" alt="">
      <p class="icons__item__desc">大牌免运</p>
    </div>
    <div class="icons__item">
      <img class="icons__item__img" src="http://www.dell-lee.com/imgs/vue3/红包.png" alt="">
      <p class="icons__item__desc">红包套餐</p>
    </div>
  </div>
  <div class="gap"></div>
</template>

<script>
export default {
  name: 'StaticPart'
}
</script>

<style lang="scss">
@import "../../style/variables.scss";
@import "../../style/mixins.scss";

.gap {
  height: .1rem;
  background: $content-bgColor;
  margin: 0 -.18rem;
}

.icons {
  display: flex;
  flex-wrap: wrap;
  margin-top: .16rem;

  &__item {
    width: 20%;

    &__img {
      width: .4rem;
      height: .4rem;
      display: block;
      margin: 0 auto;
    }

    &__desc {
      margin: .06rem 0 .16rem 0;
      text-align: center;
      color: $content-fontcolor;
    }
  }
}

.banner {
  height: 0;
  overflow: hidden;
  padding-bottom: 25.4%;

  .banner__img {
    width: 100%;
  }
}

.search {
  line-height: .32rem;
  background: $content-bgColor;
  color: #b7b7b7;
  border-radius: .16rem;
  font-size: .14rem;
  margin-bottom: .12rem;

  .search__icon {
    font-size: .2rem;
    display: inline-block;
    position: relative;
    top: .03rem;
    padding: 0 .12rem 0 .16rem;
  }
}

.position {
  position: relative;
  padding: .16rem .24rem .16rem 0;
  line-height: .22rem;
  font-size: .16rem;
  color: $content-fontcolor;
  @include ellipsis;

  .position__icon {
    position: relative;
    font-size: .2rem;
    top: 0.01rem;
  }

  .position_notice {
    position: absolute;
    font-size: .2rem;
    right: 0;
    top: .17rem;
  }
}
</style>
