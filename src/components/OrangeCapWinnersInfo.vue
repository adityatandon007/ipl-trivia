<template>
  <div class="container card text-center mb10">
    <h2>Orange Cap Winners Data Visualization</h2>
    <details class="mb10">
      <summary><strong>Trivia</strong></summary>
      <p><span class="cl-orange bold">Chris Gayle (aka The Universe Boss)</span> holds the most number of <span class="cl-orange bold">Orange Caps</span></p>
    </details>
    <bar-chart :data="chartData" :options="chartOptions" :styles="myStyles"></bar-chart>
	</div>
</template>

<script>
import orange_cap_winners from "../assets/orange_cap_winners.json";
export default {
  name: "OrangeCapWinnersInfo",
  components: {
    BarChart: () => import("../common/BarChart.vue")
  },
  data() {
    return {
      orange_cap_winners,
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
      const labels = this.orange_cap_winners.map(function (winner) {
        return winner.name
      })

      const data = this.orange_cap_winners.map(function (winner) {
        return winner.value
      })
      const backgroundColor = this.orange_cap_winners.map(function (winner) {
        return '#'+ Math.floor(Math.random()*16777215).toString(16);
      })
      return {
        labels: labels,
        datasets: [
          {
            label: "Orange Cap Count",
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