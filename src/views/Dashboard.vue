<template>
  <div class="d-flex flex-row">
    <div class="">
      <Sidebar />
    </div>
    <div class="home w-100 d-flex flex-column">
      <div class="w-100">
        <Search />
      </div>
      <div class="row w-100 mx-auto">
        <div
          v-for="chart in defaultCharts"
          :key="chart.title"
          class="col-12 col-xl-6"
        >
          <LineChart :data="chart" />
        </div>
      </div>
    </div>
  </div>
</template>

// @ is an alias to /src
<script lang="ts">
import Search from "../components/Search.vue";
import Sidebar from "../components/Sidebar.vue";
import HelloWorld from "../components/HelloWorld.vue";
import LineChart from "../components/LineChart.vue";
import { defineComponent } from "vue";
import computed from "vue";
export default defineComponent({
  components: {
    Search,
    Sidebar,
    LineChart,
  },
  computed: {
    defaultCharts() {
      return this.$store.state.defaultMutations;
    },
  },
});
</script>

<style lang="scss">
.home {
  margin-left: 250px;
}
</style>

