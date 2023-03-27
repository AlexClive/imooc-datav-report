<template>
  <common-card title="累计用户数" values="1,462,666">
    <transition>
      <div id="total-user-charts" :style="{width: '100%',height: '100%'}"></div>
    </transition>
    <template v-slot:footer>
      <div class="compare-wrapper">
        <div class="total-users-footer">
          <span>日同比</span><span class="emphasis">46.18%</span>
          <div class="increase"></div>
          <span class="month">月同比</span><span class="emphasis">82.72%</span>
          <div class="decrease"></div>
        </div>
      </div>
    </template>
  </common-card>
</template>

<script>
import commonCardMixin from '@/mixins/commonCardMixin'

export default {
  name: 'total-users',
  mixins: [commonCardMixin],
  mounted () {
    const myChart = document.getElementById('total-user-charts')
    const chart = this.$echarts.init(myChart)
    chart.setOption({
      grid: {
        left: 0,
        top: 0,
        right: 0,
        bottom: 0
      },
      xAxis: {
        type: 'value',
        show: false,
        boundaryGap: false,
        max: 250
      },
      yAxis: {
        type: 'category',
        show: false,
        boundaryGap: false
      },
      series: [{
        type: 'bar',
        data: [100],
        barWidth: 10,
        stack: '总量',
        itemStyle: {
          color: '#45c946'
        }
      }, {
        type: 'bar',
        data: [250],
        barWidth: 10,
        stack: '总量',
        itemStyle: {
          color: '#eee'
        }
      }, {
        type: 'custom',
        data: [100],
        stack: '总量',
        renderItem: (params, api) => {
          const value = api.value(0)
          const endPoint = api.coord([value, 0])
          return {
            type: 'group',
            position: endPoint,
            children: [{
              type: 'path',
              shape: {
                d: 'M65.582671 288.791335l446.417329 446.41733 446.417329-446.41733z',
                x: -5,
                y: -20,
                width: 10,
                height: 10,
                layout: 'cover'
              },
              style: {
                fill: '#45c946'
              }
            }, {
              type: 'path',
              shape: {
                d: 'M65.582671 735.208665l446.417329-446.41733 446.417329 446.41733z',
                x: -5,
                y: 10,
                width: 10,
                height: 10,
                layout: 'cover'
              },
              style: {
                fill: '#45c946'
              }
            }]

          }
        }
      }]
    })
  }
}
</script>

<style scoped lang="scss">
.total-users-footer {
  display: flex;
  align-items: center;

  .month {
    margin-left: 10px;
  }
}
</style>
