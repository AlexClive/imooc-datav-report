<template>
  <common-card
    title="累计订单量"
    values="2,979,593">
    <template>
      <v-chart :option="getOptions()"></v-chart>
    </template>
    <template v-slot:footer>
      <span>昨日订单量</span>
      <span class="emphasis">2,000,000</span>
    </template>

  </common-card>
</template>

<script>
import commonCardMixin from '@/mixins/commonCardMixin'

export default {
  name: 'total-orders',
  mixins: [commonCardMixin],
  methods: {
    getOptions () {
      return {
        xAxis: {
          type: 'category',
          boundaryGap: false,
          show: false
        },
        yAxis: {
          show: false
        },
        series: [{
          type: 'line',
          data: [410, 82, 200, 334, 390, 330, 220, 150, 82, 200, 134, 290],
          areaStyle: {
            color: 'purple'
          },
          lineStyle: {
            width: 0
          },
          itemStyle: {
            opacity: 0
          },
          smooth: true
        }],
        grid: {
          top: 0,
          right: 0,
          bottom: 0,
          left: 0
        }
      }
    }
  },
  mounted () {
  }
}
</script>
