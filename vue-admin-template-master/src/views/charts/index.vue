<template>
  <div class="chart-container">
    <div class="container-engineering">
      <chart height="400px" width="66.67%" />
    </div>
  </div>
</template>

<script>
/* eslint-disable */
import Chart from "@/components/Charts/MixChart";

export default {
  name: "MixChart",
  components: { Chart }
};
</script>

<style scoped>
.chart-container {
  position: relative;
  width: 100%;
  height: 100%;
}
.container-engineering {
  position: relative;
  width: 100%;
  height: 100%;
}
.container-completionRate {
  position: relative;
  width: 100%;
  height: 100%;
}
</style>

