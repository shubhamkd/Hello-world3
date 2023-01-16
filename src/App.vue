<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <download-excel
  ref="kpd"
    :data="jsonData"
    name="details.csv"
    type="csv"
  >
  </download-excel>
<!-- 
  <download-csv
    class   = "btn btn-default"
    :data   = "json_data"
    name    = "skd.csv">
    <button class="button">Download</button>
</download-csv> -->

    <button @click="csvDownload">Download Data</button>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import JsonExcel from "vue-json-excel3";
export default {
  name: 'App',
  components: {
    DownloadExcel: JsonExcel,
    // 'downloadCsv': JsonCSV
  },
  data() {
    return {
      jsonData: [
        {
          name: "Tony Peña",
          city: "New York",
          country: "United States",
          birthdate: "1978-03-15",
        },
        {
          name: "Thessaloniki",
          city: "Athens",
          country: "Greece",
          birthdate: "1987-11-23",
        },
      ],
    };
  },
  methods: {
    csvDownload() {
        console.log("csvDownload");

        this.$refs.kpd.generate();
    },
  },
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
</style>
