<template>
  <div class="nearby">
    <h3 class="nearby__title">附近店铺</h3>
    <div class="nearby__item" v-for="item in nearbyList" :key="item.id">
      <img class="nearby__item__img" :src="item.imgUrl" alt="">
      <div class="nearby__item__content">
        <div class="nearby__item__content__title">{{ item.title }}</div>
        <div class="nearby__item__content__tags">
          <span
            class="nearby__item__content__tag"
            v-for="tag in item.tags"
            :key="tag">
            {{ tag }}
          </span>
        </div>
        <div class="nearby__item__content__highlight">{{ item.desc }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Nearby',
  setup () {
    const nearbyList = [
      {
        id: 1,
        title: '沃尔玛',
        tags: ['月售1万+', '起送0元', '基础运费5元'],
        desc: 'VIP尊享满89元减4元运费',
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png'
      }, {
        id: 2,
        title: '沃尔玛',
        tags: ['月售1万+', '起送0元', '基础运费5元'],
        desc: 'VIP尊享满89元减4元运费',
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png'
      }, {
        id: 3,
        title: '沃尔玛',
        tags: ['月售1万+', '起送0元', '基础运费5元'],
        desc: 'VIP尊享满89元减4元运费',
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png'
      }, {
        id: 4,
        title: '沃尔玛',
        tags: ['月售1万+', '起送0元', '基础运费5元'],
        desc: 'VIP尊享满89元减4元运费',
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png'
      }, {
        id: 5,
        title: '沃尔玛',
        tags: ['月售1万+', '起送0元', '基础运费5元'],
        desc: 'VIP尊享满89元减4元运费',
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png'
      }
    ]
    return {
      nearbyList
    }
  }
}
</script>

<style lang="scss">
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
