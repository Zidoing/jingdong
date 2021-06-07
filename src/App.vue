<template>
  <div class="docker">
    <span class="docker__item">首页</span>
    <span class="docker__item">购物车</span>
    <span class="docker__item">订单</span>
    <span class="docker__item">我的</span>
  </div>
</template>

<style lang="scss">
.docker {
  display: flex;
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 0.49rem;
  border: 1px solid #f1f1f1;
  padding: 0 .18rem;
  box-sizing: border-box;

  .docker__item {
    flex: 1;
    text-align: center;
  }
}
</style>
