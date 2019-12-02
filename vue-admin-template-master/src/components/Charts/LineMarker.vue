<template>
  <ve-histogram :data="chartData" :settings="chartSettings"></ve-histogram>
</template>

<script>
export default {
  data() {
    this.chartSettings = {
      metrics: ["维修完成率"],
      dimension: ["门店"]
    };
    return {
      chartData: {
        columns: ["门店", "维修完成率"],
        rows: [
          { "门店": "门店10", "维修完成率": "100.00%" },
      
        ]
      }
    };
  }
};
</script>