<template>
     <GChart
    :type="chartType"
    :data="chartData"
    :options="chartOptions"
  />
</template>
<style scoped>

</style>
<script>
import { GChart } from 'vue-google-charts'
export default {
    name:"Chart",
    props:["chartType","chartData","chartOptions"],
    components: {
        GChart
  },
   data () {
    return {
     
    }
    }
}
</script>
