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
    <div class="footer">
      <a class="cl-black" target="_blank" href="https://github.com/adityatandon007/ipl-trivia">
        <svg class="octicon" height="32" viewBox="0 0 16 16" version="1.1" width="32" aria-hidden="true"><path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path></svg>
        Star the project
      </a>
    </div>
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
.cl-black {
  color: #000000;
}
.footer {
  box-shadow: 0 0px 2px 2px #cccccc;
  padding: 4px;
  margin-top: 20px;
}
.octicon {
  vertical-align: middle !important;
}
</style>
