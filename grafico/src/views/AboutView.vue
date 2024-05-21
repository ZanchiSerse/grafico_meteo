<template>
  <div>
    <apexchart type="line" height="350" :options="chartOptions" :series="series"></apexchart>
  </div>
</template>

<script>
import VueApexCharts from 'vue3-apexcharts'

export default {
  components: {
    apexchart: VueApexCharts
  },
  data() {
    return {
      chartOptions: {
        chart: {
          id: 'vuechart-example'
        },
        xaxis: {
          categories: [2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021]
        },
        yaxis: [
          {
            title: {
              text: 'Temperatura Media Annuo (°C)'
            },
          },
          {
            opposite: true,
            title: {
              text: 'Precipitazione Totale Annuo (mm)'
            },
          },
        ],
        stroke: {
          curve: 'smooth'
        },
        tooltip: {
          shared: true,
          intersect: false
        }
      },
      series: [
        {
          name: 'Temperatura Media Annuo',
          type: 'line',
          data: [15.02, 15.43, 14.55, 15.09, 13.87, 15.37, 14.97, 14.41, 15.28, 14.79, 15.31, 14.67, 14.95, 15.2, 14.67, 14.56]
        },
        {
          name: 'Precipitazione Totale Annuo',
          type: 'line',
          data: [871.4, 1035.4, 1150.2, 894.2, 975.4, 485.8, 1080.8, 1203.4, 842.8, 860.8, 781.8, 585.7, 753.8, 934.2, 1376.6, 700.2]
        }
      ]
    }
  }
}
</script>

<style scoped>
#vuechart-example {
  max-width: 650px;
  margin: 35px auto;
}
</style>