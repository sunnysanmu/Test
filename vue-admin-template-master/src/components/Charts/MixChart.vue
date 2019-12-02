<template>
  <div>
    <div :id="id" :class="className" :style="{height:height,width:width}" />
  </div>
</template>

<script>
/* eslint-disable */
import echarts from "echarts";
import resize from "./mixins/resize";

export default {
  mixins: [resize],
  props: {
    className: {
      type: String,
      default: "chart"
    },
    id: {
      type: String,
      default: "chart"
    },
    width: {
      type: String,
      default: "200px"
    },
    height: {
      type: String,
      default: "200px"
    }
  },
  data() {
    return {};
  },
  mounted() {
    this.initChart();
  },
  beforeDestroy() {
    if (!this.chart) {
      return;
    }
    this.chart.dispose();
    this.chart = null;
  },
  methods: {
    initChart() {
      this.chart = echarts.init(document.getElementById(this.id));
      const xData = (function() {
        const data = [];
        for (let i = 1; i < 21; i++) {
          data.push("门店" + i);
        }
        return data;
      })();

      this.chart.setOption(
        {
          backgroundColor: "#F2F6FC",
          title: {
            text: "工程维修门店完成率",
            x: "20",
            top: "10",
            textStyle: {
              color: "#303133",
              fontSize: "22"
            },
            subtextStyle: {
              color: "#90979c",
              fontSize: "16"
            }
          },
          tooltip: {
            trigger: "axis",
            formatter: "{c}%",
            axisPointer: {
              textStyle: {
                color: "#303133"
              }
            }
          },
          grid: {
            left: "5%",
            right: "5%",
            borderWidth: 0,
            top: 150,
            bottom: 95,
            textStyle: {
              color: "#303133"
            }
          },
          legend: {
            x: "5%",
            top: "15%",
            textStyle: {
              color: "#90979c"
            },
            data: ["完成率"]
          },
          calculable: true,
          xAxis: [
            {
              type: "category",
              axisLine: {
                lineStyle: {
                  color: "#90979c"
                }
              },
              splitLine: {
                show: false
              },
              axisTick: {
                show: false
              },
              splitArea: {
                show: false
              },
              axisLabel: {
                interval: 0
              },
              data: xData
            }
          ],
          yAxis: [
            {
              type: "value",
              splitLine: {
                show: false
              },
              axisLine: {
                show: true,
                interval: "auto",
                formatter: "{value}%",
                lineStyle: {
                  color: "#90979c"
                }
              },
              axisTick: {
                show: false
              },
              axisLabel: {
                interval: 0
              },
              splitArea: {
                show: false
              }
            }
          ],
          /* dataZoom: [
          {
            show: true,
            height: 30,
            xAxisIndex: [0],
            bottom: 30,
            start: 10,
            end: 80,
            handleIcon:
              "path://M306.1,413c0,2.2-1.8,4-4,4h-59.8c-2.2,0-4-1.8-4-4V200.8c0-2.2,1.8-4,4-4h59.8c2.2,0,4,1.8,4,4V413z",
            handleSize: "110%",
            handleStyle: {
              color: "#d3dee5"
            },
            textStyle: {
              color: "#fff"
            },
            borderColor: "#90979c"
          },
          {
            type: "inside",
            show: true,
            height: 15,
            start: 1,
            end: 35
          }
        ],*/
          series: [
            {
              name: "完成率",
              type: "bar",
              stack: "total",
              barWidth: 15,
              barGap: "10%",
              itemStyle: {
                normal: {
                  color: "#83A7D1",
                  label: {
                    show: true,
                    textStyle: {
                      color: "#303133"
                    },
                    position: "top",
                    formatter: "{b}\n{c}% "
                  }
                }
              },
              data: [
                100,
                100,
                90,
                85,
                80,
                70,
                60,
                60,
                58,
                57,
                56,
                53,
                51,
                51,
                50,
                50,
                45,
                30,
                13,
                12
              ]
            }
          ]
        },
        {
          backgroundColor: "#F2F6FC",
          title: {
            text: "工程维修门店完成率",
            x: "20",
            top: "10",
            textStyle: {
              color: "#303133",
              fontSize: "22"
            },
            subtextStyle: {
              color: "#90979c",
              fontSize: "16"
            }
          },
          tooltip: {
            trigger: "axis",
            formatter: "{c}%",
            axisPointer: {
              textStyle: {
                color: "#303133"
              }
            }
          },
          grid: {
            left: "5%",
            right: "5%",
            borderWidth: 0,
            top: 150,
            bottom: 95,
            textStyle: {
              color: "#303133"
            }
          },
          legend: {
            x: "5%",
            top: "15%",
            textStyle: {
              color: "#90979c"
            },
            data: ["完成率"]
          },
          calculable: true,
          xAxis: [
            {
              type: "category",
              axisLine: {
                lineStyle: {
                  color: "#90979c"
                }
              },
              splitLine: {
                show: false
              },
              axisTick: {
                show: false
              },
              splitArea: {
                show: false
              },
              axisLabel: {
                interval: 0
              },
              data: xData
            }
          ],
          yAxis: [
            {
              type: "value",
              splitLine: {
                show: false
              },
              axisLine: {
                show: true,
                interval: "auto",
                formatter: "{value}%",
                lineStyle: {
                  color: "#90979c"
                }
              },
              axisTick: {
                show: false
              },
              axisLabel: {
                interval: 0
              },
              splitArea: {
                show: false
              }
            }
          ],
          /* dataZoom: [
          {
            show: true,
            height: 30,
            xAxisIndex: [0],
            bottom: 30,
            start: 10,
            end: 80,
            handleIcon:
              "path://M306.1,413c0,2.2-1.8,4-4,4h-59.8c-2.2,0-4-1.8-4-4V200.8c0-2.2,1.8-4,4-4h59.8c2.2,0,4,1.8,4,4V413z",
            handleSize: "110%",
            handleStyle: {
              color: "#d3dee5"
            },
            textStyle: {
              color: "#fff"
            },
            borderColor: "#90979c"
          },
          {
            type: "inside",
            show: true,
            height: 15,
            start: 1,
            end: 35
          }
        ],*/
          series: [
            {
              name: "完成率",
              type: "bar",
              stack: "total",
              barWidth: 150,
              barGap: "10%",
              itemStyle: {
                normal: {
                  color: "#83A7D1",
                  label: {
                    show: true,
                    textStyle: {
                      color: "#303133"
                    },
                    position: "top",
                    formatter: "{b}\n{c}% "
                  }
                }
              },
              data: [
                10,
                10,
                90,
                8,
                8,
                7,
                6,
                6,
                58,
                57,
                56,
                53,
                51,
                51,
                50,
                5,
                45,
                3,
                13,
                12
              ]
            }
          ]
        }
      );
    }
  }
};
</script>
