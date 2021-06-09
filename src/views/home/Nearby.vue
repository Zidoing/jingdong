<template>
  <div class="nearby">
    <h3 class="nearby__title">附近店铺</h3>
    <div class="nearby__item" v-for="item in nearbyList" :key="item._id">
      <img class="nearby__item__img" :src="item.imgUrl" alt="">
      <div class="nearby__item__content">
        <div class="nearby__item__content__title">{{ item.name }}</div>
        <div class="nearby__item__content__tags">
          <span class="nearby__item__content__tag">月售:{{ item.sales }}</span>
          <span class="nearby__item__content__tag">起送:{{ item.expressLimit }}</span>
          <span class="nearby__item__content__tag">基础运费:{{ item.expressPrice }}</span>
        </div>
        <div class="nearby__item__content__highlight">{{ item.slogan }}</div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
import { get } from '@/utils/request'

const useNearbyListEffect = () => {
  const nearbyList = ref([])
  const getNearbyList = async () => {
    const result = await get('/api/shop/hot-list')
    console.log(result)
    if (result?.errno === 0 && result?.data.length) {
      nearbyList.value = result.data
    }
  }

  return {
    getNearbyList,
    nearbyList
  }
}

export default {
  name: 'Nearby',
  setup () {
    const {
      getNearbyList,
      nearbyList
    } = useNearbyListEffect()

    getNearbyList()
    return {
      nearbyList
    }
  }
}
</script>

<style lang="scss" scoped>
@import "../../style/variables.scss";
@import "../../style/mixins.scss";

.nearby {
  &__title {
    margin: .16rem 0 .02rem 0;
    color: $content-fontcolor;
    font-size: .18rem;
    font-weight: normal;
  }

  &__item {
    display: flex;
    padding-top: .12rem;

    &__img {
      width: .56rem;
      height: .56rem;
      margin-right: .16rem;
    }

    &__content {
      flex: 1;
      border-bottom: 1px solid $content-bgColor;
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
}
</style>
