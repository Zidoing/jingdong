<template>
  <div class="wrapper">
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
  </div>
  <div class="docker">
    <span class="docker__item docker__item--active">
      <div class="iconfont">&#xe89c;</div>
      <div class="docker__title">首页</div>
    </span>
    <span class="docker__item">
      <div class="iconfont">&#xe705;</div>
      <div class="docker__title">购物车</div>
    </span>
    <span class="docker__item">
      <div class="iconfont">&#xe621;</div>
      <div class="docker__title">订单</div>
    </span>
    <span class="docker__item">
      <div class="iconfont">&#xe681;</div>
      <div class="docker__title">我的</div>
    </span>
  </div>
</template>

<style lang="scss">
@import "./style/variables.scss";
@import "./style/mixins.scss";

.wrapper {
  position: absolute;
  left: 0;
  top: 0;
  bottom: .5rem;
  right: 0;
  padding: 0 .18rem;

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
    background: #f1f1f1;
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

}

.docker {
  display: flex;
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 0.49rem;
  border: .01rem solid #f1f1f1;
  padding: 0 .18rem;
  box-sizing: border-box;
  color: $content-fontcolor;

  &__item {
    flex: 1;
    text-align: center;

    &--active {
      color: #1fa4fc;
    }

    .iconfont {
      font-size: .18rem;
      margin: 0.07rem 0 0.02rem 0;
    }
  }

  &__title {
    font-size: .2rem;
    transform: scale(0.5, 0.5);
    transform-origin: center top;
  }

}
</style>
