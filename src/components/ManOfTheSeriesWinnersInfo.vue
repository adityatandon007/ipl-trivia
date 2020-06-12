<template>
  <div class="container card text-center mb10">
    <h2>Man of the Series Winners Data Visualization</h2>
    <details class="mb10">
      <summary><strong>Trivia</strong></summary>
      <p><span class="cl-golden bold">Shane Watson</span> holds the most number of <span class="cl-golden bold">Man of the Series</span></p>
    </details>
    <bar-chart :data="chartData" :options="chartOptions" :styles="myStyles"></bar-chart>
	</div>
</template>

<script>
import man_of_the_series_winners from "../assets/man_of_the_series_winners.json";
export default {
  name: "ManOfTheSeriesWinnersInfo",
  components: {
    BarChart: () => import("../common/BarChart.vue")
  },
  data() {
    return {
      man_of_the_series_winners,
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
      const labels = this.man_of_the_series_winners.map(function (winner) {
        return winner.name
      })
      const data = this.man_of_the_series_winners.map(function (winner) {
        return winner.value
      })
      const backgroundColor = this.man_of_the_series_winners.map(function (winner) {
        return '#'+ Math.floor(Math.random()*16777215).toString(16);
      })
      return {
        labels: labels,
        datasets: [
          {
            label: "Man of the Series Count",
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