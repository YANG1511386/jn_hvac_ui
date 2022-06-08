<template>
  <div class="co2_contain">
    <img width="100%" height="600" style="display: inline-block;" src="../assets/IotPlatfrom/image003.jpeg" alt="" srcset="">
    <div id="Co2" class="co2"></div>
  </div>
</template>

<style scoped>
.co2_contain {
  display: flex;
}

.co2{
    position: absolute; 
    width: 536px; 
    height: 558px; 
    padding: 0px; 
    margin: 0px;
    border-width: 0px; 
    cursor: default;
}
</style>

<script>
import * as echarts from "echarts/core";
import { GridComponent } from 'echarts/components';
import { LineChart } from 'echarts/charts';
import { UniversalTransition } from 'echarts/features';
import { CanvasRenderer } from 'echarts/renderers';



echarts.use([GridComponent, LineChart, CanvasRenderer, UniversalTransition]);
export default {
  data() {
    return {
    };
    
  },
    mounted(){

      this.drawLine()

  },
  methods: {
    drawLine() {
      let chartDom = document.getElementById("Co2");
      this.myChart = echarts.init(chartDom);
     


      this.myChart.setOption( {
  xAxis: {
    type: 'category',
    data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
  },
  yAxis: {
    type: 'value'
  },
  series: [
    {
      data: [150, 230, 224, 218, 135, 147, 260],
      type: 'line'
    }
  ]
}
);
    },
  },
};
</script>

<style>
</style>