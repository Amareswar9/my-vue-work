<template>
    <div class="card" v-bind:class="[theme]" v-bind:style="{width:width}">
        <div class="card-head df">
         <div class="title">
             {{title}}
        </div>
        <FilterComponent :filters="filters"/>
        </div>
        <div class="card-body">
            <Chart v-for="chart in charts" :key="chart._id" :chart-type="chart.chartType" :chart-data="chart.chartData" :chart-options="chart.chartOptions"/>
            <Widget1 v-for="widget in widgets" :key="widget.id" :content="widget.content" :alertType="widget.alertType" :title="widget.title" />
        </div>
       
    </div>
</template>
<style scoped>
.card{
    height: 326px;
    margin: 18px;
    border-radius: 4px;
    position: relative;
}
.light{
    background: #323232;
}
.dark{
    background: #0F0F0F
}
.card-head{
    color: white;
    padding: 0px 24px;
    font-size: 16px;
    font-weight: bold;
    justify-content: space-between;
    align-items: center;
    height: 44px;
}
.card-body{
    position: absolute;
    top: 44px;
    bottom: 0;
    left: 0;
    right: 0;
   
}
</style>
<script>
import FilterComponent from './Filter.vue'
import Chart from './Chart.vue'
import Widget1 from './widgets/Widget1'
export default {
    name:"Card",
    props:["title","theme","width","filters","charts","widgets"],
    components:{FilterComponent,Chart,Widget1},
    data:()=>{
        return {
            
        }
    }
}
</script>
