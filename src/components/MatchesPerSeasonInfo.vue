<template>
  <div class="container card text-center mb10">
    <h2>Matches Per Season Data Visualization</h2>
    <details class="mb10">
      <summary><strong>Trivia</strong></summary>
      <p>Most matched were played in <span class="text-primary bold">Season 6</span></p>
    </details>
    <line-chart :data="chartData" :options="chartOptions" :styles="myStyles"></line-chart>
	</div>
</template>

<script>
import matches_per_season from "../assets/matches_per_season.json";
export default {
  name: "MatchesPerSeasonInfo",
  components: {
    LineChart: () => import("../common/LineChart.vue")
  },
  data() {
    return {
      matches_per_season,
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
      const labels = this.matches_per_season.map(function (season) {
        return season.name
      })
      const data = this.matches_per_season.map(function (season) {
        return season.value
      })
      return {
        labels: labels,
        datasets: [
          {
            label: "Matches",
            backgroundColor: '#1bed3c',
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