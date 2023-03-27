<template>
  <common-card
    title="累计销售额"
    values="￥ 32,039,165"
  >
    <template>
      <div class="compare-wrapper">
        <div class="compare">
          <span>日同比</span><span class="emphasis"> 7.33</span>
          <div class="increase"></div>
        </div>
        <div class="compare">
          <span>月同比</span><span class="emphasis"> 7.33</span>
          <div class="decrease"></div>
        </div>
      </div>
    </template>
    <template v-slot:footer>
      <span>昨日销售额</span>
      <span class="emphasis">￥ 30,000,000</span>
    </template>
  </common-card>
</template>

<script>
import commonCardMixin from '@/mixins/commonCardMixin'

export default {
  name: 'total-sales',
  mixins: [commonCardMixin]
}
</script>

<style scoped lang="scss">
.compare-wrapper {
  height: 100%;

  .compare {
    display: flex;
    align-items: center;
    margin-top: 3px;
    color: #666;
  }
}

span {
  font-size: 12px;
}
</style>
