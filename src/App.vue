<template>
  <div id="app">
    <div class="d-inline-block">
      <rough-bar
        :data="{
          labels: ['North', 'South', 'East', 'West'],
          values: [10, 5, 8, 3],
        }"
        title="Regions"
        roughness="8"
        :colors="['red', 'orange', 'blue', 'skyblue']"
        stroke="black"
        stroke-width="3"
        fill-style="cross-hatch"
        fill-weight="3.5"
      />
    </div>
    <div class="d-inline-block">
      <rough-pie
        :data="{
          labels: ['North', 'South', 'East', 'West'],
          values: [10, 5, 8, 3],
        }"
        title="Covid-19 Chart"
        roughness="8"
        :colors="['red', 'orange', 'blue', 'skyblue']"
        stroke="black"
        stroke-width="3"
        fill-style="cross-hatch"
        fill-weight="3.5"
      />
    </div>
  </div>
</template>

<script>
import { RoughBar } from "vue-roughviz";
import { RoughPie } from "vue-roughviz";
export default {
  name: "App",
  components: {
    RoughBar,
    RoughPie,
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
  margin: 10px;
}
</style>
