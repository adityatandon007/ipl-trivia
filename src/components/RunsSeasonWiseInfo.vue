<template>
  <div class="container card text-center mb10">
    <h2>Runs Per Season Data Visualization</h2>
    <details class="mb10">
      <summary><strong>Trivia</strong></summary>
      <p><span class="text-primary bold">Season 6</span> recorded the most runs</p>
    </details>
    <line-chart :data="chartData" :options="chartOptions" :styles="myStyles"></line-chart>
	</div>
</template>

<script>
import runs_seasonwise from "../assets/runs_seasonwise.json";
export default {
  name: "RunsSeasonWiseInfo",
  components: {
    LineChart: () => import("../common/LineChart.vue")
  },
  data() {
    return {
      runs_seasonwise,
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          yAxes: [{
            ticks: {
              beginAtZero: false,
            }
          }]
        }
      },
      isMobile: false
    };
  },
  computed: {
    chartData: function () {
      const labels = this.runs_seasonwise.map(function (season) {
        return season.name
      })
      const data = this.runs_seasonwise.map(function (season) {
        return season.value
      })
      return {
        labels: labels,
        datasets: [
          {
            label: "Runs",
            backgroundColor: '#3e92ad',
            data: data
          }
        ]
      }
    },
    myStyles () {
      return {
        height: '70vh',
        margin: 'auto',
        position: 'relative'
      }
    }
  }
};
</script>

<style >
</style>