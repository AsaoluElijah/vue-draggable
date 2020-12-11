<template>
  <div id="app">
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
      class="d-inline"
    />
  </div>
</template>

<script>
import { RoughBar } from "vue-roughviz";
export default {
  name: "App",
  components: {
    RoughBar,
  },
};
</script> 