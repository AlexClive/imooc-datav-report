<template>
  <div class="home">
    <top-view/>
    <salse-view/>
    <bootom-view/>
    <map-View/>
  </div>
</template>

<script>
import TopView from '../components/TopView/index.vue'
import SalseView from '../components/SalseView/index.vue'
import BootomView from '../components/BootomView/index.vue'
import MapView from '../components/MapView/index.vue'

export default {
  name: 'HomeView',
  components: {
    TopView,
    SalseView,
    BootomView,
    MapView
  }
}
</script>
<style>
.home {
  width: 100%;
  height: 100%;
  padding: 20px;
  background: #eee;
  box-sizing: border-box;
}
</style>
