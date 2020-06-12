<template>
  <div class="container card text-center mb10">
    <h2>Host Country Data Visualization</h2>
    <details class="mb10">
      <summary><strong>Trivia</strong></summary>
      <p>It's no surprise. Most of the matches have been held in <span class="cl-dark-blue bold">India</span> since it's an Indian Premeire League.</p>
    </details>
    <pie-chart :data="chartData" :options="chartOptions" :styles="myStyles"></pie-chart>
	</div>
</template>

<script>
import host_country from "../assets/host_country.json";
export default {
  name: "HostCountryInfo",
  components: {
    PieChart: () => import("../common/PieChart.vue")
  },
  data() {
    return {
      host_country,
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
      },
      isMobile: false
    };
  },
  computed: {
    chartData: function () {
      const labels = this.host_country.map(function (country) {
        return country.name
      })
      const data = this.host_country.map(function (country) {
        return country.value
      })
      const backgroundColor = this.host_country.map(function (country) {
        return '#'+ Math.floor(Math.random()*16777215).toString(16);
      })
      return {
        labels: labels,
        datasets: [
          {
            label: "Host Country Info",
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