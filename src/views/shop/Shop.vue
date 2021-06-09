<template>
  <div class="wrapper">
    <ShopInfo :item="item" :hide-border="true"/>
  </div>
</template>

<script>
import ShopInfo from '@/components/ShopInfo'

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
    return {
      item
    }
  }
}
</script>

<style scoped lang="scss">
.wrapper {
  padding: 0 .18rem;
}

</style>
