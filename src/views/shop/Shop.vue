<template>
  <div class="wrapper">
    <div class="search">
      <div class="search__back iconfont" @click="handleBackClick">&#xe677;</div>
      <div class="search__content">
        <span class="search__content__icon iconfont">&#xe725;</span>
        <input class="search__content__input" placeholder="请输入商品名称搜索">
      </div>
    </div>
    <ShopInfo :item="item" :hide-border="true"/>
  </div>
</template>

<script>
import ShopInfo from '@/components/ShopInfo'
import { useRouter } from 'vue-router'

export default {
  name: 'Shop',
  components: { ShopInfo },
  setup () {
    const item = {
      _id: '1',
      name: '111',
      imgUrl: '13213',
      sales: 111,
      expressLimit: 0,
      expressPrice: 22,
      slogan: '321312'
    }
    const router = useRouter()
    const handleBackClick = () => {
      router.back()
    }
    return {
      item,
      handleBackClick
    }
  }
}
</script>

<style scoped lang="scss">
.wrapper {
  padding: 0 .18rem;
}

.search {
  height: .32rem;
  display: flex;
  margin: .2rem 0 .16rem 0;

  &__back {
    width: .3rem;
    height: .32rem;
    text-align: center;
    line-height: .32rem;
    font-size: .2rem;
  }

  &__content {
    flex: 1;
    line-height: .32rem;
    background: #f5f5f5;
    border-radius: .16rem;
    display: flex;

    &__icon {
      width: .44rem;
      height: .32rem;
      text-align: center;
      line-height: .32rem;
      color: #b7b7b7;
    }

    &__input {
      height: .32rem;
      width: 100%;
      border: none;
      outline: none;
      background: none;
      padding-right: .2rem;
      font-size: .14rem;

      &::placeholder {
        color: #333;
      }
    }
  }
}

</style>
