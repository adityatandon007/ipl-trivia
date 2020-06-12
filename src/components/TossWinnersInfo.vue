<template>
  <div class="container card text-center mb10">
    <h2>Toss Winners Data Visualization</h2>
    <details class="mb10">
      <summary><strong>Trivia</strong></summary>
      <p><span class="cl-blue bold">Mumbai Indians</span> have been winning most of the tosses in the IPL</p>
    </details>
    <bar-chart :data="chartData" :options="chartOptions" :styles="myStyles"></bar-chart>
	</div>
</template>
<script>
import toss_winners from "../assets/toss_winners.json";
export default {
  name: "TossWinnersInfo",
  components: {
    BarChart: () => import("../common/BarChart.vue")
  },
  data() {
    return {
      toss_winners,
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          yAxes: [{
            ticks: {
              beginAtZero: true,
            }
          }]
        }
      },
      isMobile: false
    };
  },
  computed: {
    chartData: function () {
      const labels = this.toss_winners.map(function (winner) {
        return winner.name
      })
      const data = this.toss_winners.map(function (winner) {
        return winner.value
      })
      const backgroundColor = this.toss_winners.map(function (winner) {
        return '#'+ Math.floor(Math.random()*16777215).toString(16);
      })
      return {
        labels: labels,
        datasets: [
          {
            label: "Toss Count",
            backgroundColor: backgroundColor,
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