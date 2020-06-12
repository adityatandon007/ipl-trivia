<template>
  <div id="app">
    <h1 id="titleheading">IPL Trivia 2008 - 2016</h1>
    <HostCountryInfo />
    <TossWinnersInfo />
    <OrangeCapWinnersInfo />
    <PurpleCapWinnersInfo />
    <ManOfTheSeriesWinnersInfo />
    <MatchesPerSeasonInfo />
    <RunsSeasonWiseInfo />
  </div>
</template>

<script>
import HostCountryInfo from "./components/HostCountryInfo.vue";
import TossWinnersInfo from "./components/TossWinnersInfo.vue";
import OrangeCapWinnersInfo from "./components/OrangeCapWinnersInfo.vue";
import PurpleCapWinnersInfo from "./components/PurpleCapWinersInfo.vue";
import ManOfTheSeriesWinnersInfo from "./components/ManOfTheSeriesWinnersInfo.vue";
import MatchesPerSeasonInfo from "./components/MatchesPerSeasonInfo.vue";
import RunsSeasonWiseInfo from "./components/RunsSeasonWiseInfo.vue";
export default {
  name: 'App',
  components: {
    HostCountryInfo,
    TossWinnersInfo,
    OrangeCapWinnersInfo,
    PurpleCapWinnersInfo,
    ManOfTheSeriesWinnersInfo,
    MatchesPerSeasonInfo,
    RunsSeasonWiseInfo
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
:focus {
  outline: none;
}
.mb10 {
  margin-bottom: 10px !important;
}
.bold {
  font-weight: bold !important;
}
.cl-dark-blue {
  color: #214cea;
}
.cl-purple {
  color: #8b048b;
}
.cl-orange {
  color: #e88723;
}
.cl-blue {
  color: #00a1ff;
}
.cl-golden {
  color: #a08710;
}
</style>
