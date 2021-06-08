<template>
  <div class="docker">
    <span
      :class="{'docker__item': true, 'docker__item--active': index === 0}"
      v-for="(item, index) in dockerList" :key="item.icon">
      <div class="iconfont" v-html="item.icon"></div>
      <div class="docker__title">{{ item.text }}</div>
    </span>
  </div>
</template>

<script>
export default {
  name: 'Docker',
  setup () {
    const dockerList = [
      {
        icon: '&#xe89c;',
        text: '首页'
      }, {
        icon: '&#xe705;',
        text: '购物车'
      }, {
        icon: '&#xe621;',
        text: '订单'
      }, {
        icon: '&#xe681;',
        text: '我的'
      }
    ]

    return {
      dockerList
    }
  }
}
</script>

<style lang="scss">
@import "../../style/variables.scss";
@import "../../style/mixins.scss";

.docker {
  display: flex;
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 0.49rem;
  border: .01rem solid $content-bgColor;
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
