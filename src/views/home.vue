<template>
  <div>
    <vue3-chart-js
      :id="doughnutChart.id"
      :type="doughnutChart.type"
      :data="doughnutChart.data"
      :options="doughnutChart.options"
      @before-render="beforeRenderLogic"
    ></vue3-chart-js>
  </div>
</template>

<script>
import Vue3ChartJs from '@j-t-mcc/vue3-chartjs'

export default {
  name: 'home',
  components: {
    Vue3ChartJs,
  },
  setup () {
    const doughnutChart = {
      id: 'doughnut',
      type: 'line',
      data: {
        datasets:[{
          label: 'vue',
          borderColor: '#fa9',
          backgroundColor: '#fa9',
          data: [{
            x: '7月',
            y: 40
          }, {
            x: '8月',
            y: 50
          }]
        }, {
          label: 'react',
          fill: false,
          borderColor: '#3f7',
          backgroundColor: '#3f7',
          data: [{
            x: '7月',
            y: 60
          }, {
            x: '8月',
            y: 90
          }]
        }]
      },
      options: {
        responsive: true,
        plugins: {
          legend: {
            position: 'top',
          },
          title: {
            display: true,
            text: 'chart js'
          }
        },
        interaction: {
          mode: 'index',
          intersect: false
        }
      }
    }

    const beforeRenderLogic = (event) => {
      //...
      //if(a === b) {
      //  event.preventDefault()
      //}
    }

    return {
      doughnutChart,
      beforeRenderLogic
    }
  },
}
</script>