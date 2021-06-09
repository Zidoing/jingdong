<template>
  <div class="wrapper">
    <div class="search">
      <div class="search__back iconfont" @click="handleBackClick">&#xe677;</div>
      <div class="search__content">
        <span class="search__content__icon iconfont">&#xe725;</span>
        <input class="search__content__input" placeholder="请输入商品名称搜索">
      </div>
    </div>
    <ShopInfo :item="data.item" :hide-border="true"/>
    <Content/>
  </div>
</template>

<script>
import ShopInfo from '@/components/ShopInfo'
import { useRouter, useRoute } from 'vue-router'
import { reactive } from 'vue'
import { get } from '@/utils/request'
import Content from '@/views/shop/Content'

export default {
  name: 'Shop',
  components: {
    Content,
    ShopInfo
  },
  setup () {
    const data = reactive({
      item: {}
    })

    const route = useRoute()

    const getItemData = async () => {
      const result = await get(`/api/shop/${route.params.id}`)
      console.log(result)
      if (result?.errno === 0 && result?.data) {
        data.item = result.data
      }
    }

    getItemData()
    const router = useRouter()
    const handleBackClick = () => {
      router.back()
    }

    return {
      data,
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
  margin: .14rem 0 .04rem 0;

  &__back {
    width: .3rem;
    height: .32rem;
    text-align: center;
    line-height: .32rem;
    font-size: .2rem;
    color: #b6b6b6;
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
