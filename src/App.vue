<template>
  <div id="app">
    <div class="d-inline-block">
      <rough-bar
        v-if="chartValue.length > 0"
        :data="{
          labels: chartLabel,
          values: chartValue,
        }"
        title="BTC - 10 Days"
        roughness="3"
        color="#ccc"
        stroke="black"
        stroke-width="1"
        fill-style="zig-zag"
        fill-weight="2"
      />
    </div>
  </div>
</template>

<script>
import { RoughBar } from "vue-roughviz";
export default {
  name: "App",
  components: {
    RoughBar,
  },
  data() {
    return {
      chartLabel: [],
      chartValue: [],
    };
  },
  methods: {
    async loadData() {
      await fetch(
        "https://api.coingecko.com/api/v3/coins/bitcoin/market_chart?vs_currency=usd&days=10&interval=daily"
      )
        .then((res) => res.json())
        .then((rawData) => {
          console.table(rawData.prices);
          rawData.prices.map((data) => {
            let date = new Date(data[0]).toDateString();
            let rPrice = data[1];
            console.log(`Price of 1btc on ${date} is ${rPrice}`);
            this.chartLabel.push(date);
            this.chartValue.push(rPrice);
          });
        })
        .catch((err) => console.error("Fetch error -> ", err));
    },
  },
  beforeMount() {
    this.loadData();
  },
};
</script>
<style scoped>
#app {
  text-align: center;
  margin-top: 10vh;
}
.d-inline-block {
  display: inline-block;
}
</style>
