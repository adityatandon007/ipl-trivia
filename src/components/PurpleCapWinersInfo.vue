<template>
  <div class="container card text-center mb10">
    <h2>Purple Cap Winners Data Visualization</h2>
    <details class="mb10">
      <summary><strong>Trivia</strong></summary>
      <p><span class="cl-purple bold">Dwayne Bravo</span> holds the most number of <span class="cl-purple bold">Purple Caps</span></p>
    </details>
    <bar-chart :data="chartData" :options="chartOptions" :styles="myStyles"></bar-chart>
	</div>
</template>

<script>
import purple_cap_winners from "../assets/purple_cap_winners.json";
export default {
  name: "PurpleCapWinnersInfo",
  components: {
    BarChart: () => import("../common/BarChart.vue")
  },
  data() {
    return {
      purple_cap_winners,
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          yAxes: [{
            ticks: {
              beginAtZero: true,
              stepSize : 1
            }
          }]
        }
      },
      isMobile: false
    };
  },
  computed: {
    chartData: function () {
      const labels = this.purple_cap_winners.map(function (winner) {
        return winner.name
      })
      const data = this.purple_cap_winners.map(function (winner) {
        return winner.value
      })
      const backgroundColor = this.purple_cap_winners.map(function (winner) {
        return '#'+ Math.floor(Math.random()*16777215).toString(16);
      })
      return {
        labels: labels,
        datasets: [
          {
            label: "Purple Cap Count",
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