<template>
  <div class="content">
    <div class="category">
      <div class="category__item"
           :class="{'category__item--active': currentTab === item.tab}"
           v-for="item in categories"
           @click="handleCategoryClick(item.tab)"
           :key="item.name">{{ item.name }}
      </div>
    </div>
    <div class="product">
      <div class="product__item" v-for="item in contentList" :key="item._id">
        <img class="product__item__img" :src="item.imgUrl" alt="">
        <div class="product__item__detail">
          <h4 class="product__item__title">{{ item.name }}</h4>
          <p class="product__item__sales">月售{{ item.sales }}件</p>
          <p class="product__item__price">
            <span class="product__item__price__yen">&yen;{{ item.price }}元</span>
            <span class="product__item__price__origin">&yen;{{ item.oldPrice }}元</span>
          </p>
        </div>
        <div class="product__number">
          <span class="product__number__minus">-</span>
          0
          <span class="product__number__plus">+</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { get } from '@/utils/request'
import { reactive, toRefs } from 'vue'

export default {
  name: 'Content',
  setup () {
    const data = reactive({
      contentList: [1, 2, 3],
      currentTab: 'all'
    })

    const categories = [{
      name: '全部商品',
      tab: 'all'
    }, {
      name: '秒杀',
      tab: 'seckill'
    }, {
      name: '新鲜水果',
      tab: 'fruit'
    }]

    const getContentData = async (tab) => {
      const result = await get('api/shop/1/products', {
        tab: tab
      })
      if (result?.errno === 0 && result?.data.length) {
        data.contentList = result.data
      }
    }
    const handleCategoryClick = (tab) => {
      getContentData(tab)
      data.currentTab = tab
      console.log('sss')
    }

    getContentData('all')

    const {
      contentList,
      currentTab
    } = toRefs(data)
    return {
      contentList,
      currentTab,
      categories,
      getContentData,
      handleCategoryClick
    }
  }
}
</script>

<style scoped lang="scss">
@import "../../style/mixins.scss";

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
    position: relative;

    &__detail {
      overflow: hidden;
    }

    .product__number {
      position: absolute;
      right: .18rem;
      bottom: .12rem;

      &__minus, &__plus {
        width: .2rem;
        height: .2rem;
        display: inline-block;
        border-radius: 50%;
        border: .01rem solid #666;
        text-align: center;
        line-height: .18rem;
        font-size: .2rem;
        color: #666;
      }

      &__plus {
        background: #0091ff;
        border: none;
        color: #fff;
        margin-left: .05rem;
      }

      &__minus {
        margin-right: .05rem;
      }
    }

    &__title {
      line-height: .2rem;
      font-size: .14rem;
      color: #333;
      margin: 0;
      @include ellipsis;
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
