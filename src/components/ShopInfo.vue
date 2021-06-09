<template>
  <div class="shop">
    <img class="shop__img" :src="item.imgUrl" alt="">
    <div :class="{shop__content:true, 'shop__content--bordered': !hideBorder}">
      <div class="shop__content__title">{{ item.name }}</div>
      <div class="shop__content__tags">
        <span class="shop__content__tag">月售:{{ item.sales }}</span>
        <span class="shop__content__tag">起送:{{ item.expressLimit }}</span>
        <span class="shop__content__tag">基础运费:{{ item.expressPrice }}</span>
      </div>
      <div class="shop__content__highlight">{{ item.slogan }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ShopInfo',
  props: ['item', 'hideBorder']
}
</script>

<style scoped lang="scss">
@import "../style/variables.scss";
@import "../style/mixins.scss";

.shop {
  display: flex;
  padding-top: .12rem;

  &__img {
    width: .56rem;
    height: .56rem;
    margin-right: .16rem;
  }

  &__content {
    flex: 1;

    &--bordered {
      border-bottom: 1px solid $content-bgColor;
    }

    padding-bottom: .12rem;

    &__title {
      line-height: .22rem;
      font-size: .16rem;
      color: $content-fontcolor;
    }

    &__tags {
      line-height: .18rem;
      font-size: .13rem;
      color: $content-fontcolor;
      margin-top: .08rem;
    }

    &__tag {
      margin-right: .16rem;
    }

    &__highlight {
      line-height: .18rem;
      font-size: .13rem;
      color: #e93b3b;
      margin: .08rem 0 0 0;
    }
  }
}
</style>
