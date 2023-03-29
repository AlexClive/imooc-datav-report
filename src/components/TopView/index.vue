<template>
  <el-row :gutter="10">
    <el-col :span="6">
      <el-card>
        <total-sales></total-sales>
      </el-card>
    </el-col>
    <el-col :span="6">
      <el-card>
        <total-orders></total-orders>
      </el-card>
    </el-col>
    <el-col :span="6">
      <el-card>
        <today-users></today-users>
      </el-card>
    </el-col>
    <el-col :span="6">
      <el-card>
        <total-users></total-users>
      </el-card>
    </el-col>
  </el-row>
</template>

<script>
import TotalOrders from '@/components/TotalOrders/index.vue'
import TotalSales from '@/components/TotalSales/index.vue'
import TotalUsers from '@/components/TotalUsers/index.vue'
import TodayUsers from '@/components/TodayUsers/index.vue'

export default {
  name: 'top-view',
  components: { TodayUsers, TotalUsers, TotalSales, TotalOrders }
}
</script>

<style scoped>

</style>
