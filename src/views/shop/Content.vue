<template>
  <div class="content">
    <div class="category">
      <div class="category__item category__item--active">全部商品</div>
      <div class="category__item">秒杀</div>
      <div class="category__item">新鲜水果</div>
      <div class="category__item">休闲食品</div>
      <div class="category__item">时令蔬菜</div>
      <div class="category__item">肉蛋家禽</div>
    </div>
    <div class="product">
      <div class="product__item">
        <img class="product__item__img" src="http://www.dell-lee.com/imgs/vue3/near.png" alt="">
        <div class="product__item__detail">
          <h4 class="product__item__title">樱桃</h4>
          <p class="product__item__sales">月售10件</p>
          <p class="product__item__price">
            <span class="product__item__price__yen">&yen;33yuan</span>
            <span class="product__item__price__origin">&yen;33yuan</span>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Content'
}
</script>

<style scoped lang="scss">
.content {
  display: flex;
  position: absolute;
  left: 0;
  right: 0;
  top: 1.5rem;
  bottom: .5rem;
}

.product {
  flex: 1;
  overflow-y: scroll;

  &__item {
    display: flex;
    padding: .12rem 0;
    margin: 0 .16rem;
    border-bottom: 0.01rem solid #f1f1f1;

    &__title {
      line-height: .2rem;
      font-size: .14rem;
      color: #333;
      margin: 0;
    }

    &__sales {
      margin: .06rem 0;
      line-height: .16rem;
      font-size: .12rem;
      color: #333;
    }

    &__price {
      margin: 0;
      line-height: .2rem;
      font-size: .14rem;
      color: #e93b3b;

      &__yen {
        font-size: .12rem;
      }

      &__origin {
        font-size: .1rem;
        margin-left: .1rem;
        line-height: .2rem;
        color: #999;
        text-decoration: line-through;
      }
    }

    &__img {
      width: .68rem;
      height: .68rem;
      margin-right: .16rem;
    }
  }
}

.category {
  width: .76rem;
  background: #f5f5f5;
  height: 100%;
  overflow-y: scroll;

  &__item {
    line-height: 40px;
    text-align: center;
    font-size: .14rem;
    color: #333;

    &--active {
      background: white;
    }
  }
}
</style>
