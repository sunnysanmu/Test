<template>
  <div :id="id" :class="className" :style="{height:height,width:width}" />
</template>

<script>
let echarts = require("echarts/lib/echarts");

require("echarts/lib/chart/bar");
require("echarts/lib/component/tooltip");
require("echarts/lib/component/title");

export default {
  name: "hello",
  data() {
    return {};
  },
  mounted() {
    this.initChart();
  },

  methods: {
    initCharts() {
      this.chart = echarts.init(this.$el);
      this.setOptions();
    },
    setOptions() {
      this.chart.setOption({
        title: {
          text: "ECharts 入门示例"
        },
        tooltip: {},
        xAxis: {
          data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
        },
        yAxis: {},
        series: [
          {
            name: "销量",
            type: "bar",
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      });
    }
  }
};
</script>
<style></style>