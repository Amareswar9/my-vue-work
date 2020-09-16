<template>
    <div class="" style="width:100%" >
        <div>
   <input type="file" value="upload" accept=".csv" @change="loadFile"/>
        <input type="button" value="Plot Chart" @click="readData" ref="tFile"/>
    
        </div>
        <div style="width:100%;height:400px">
            <Chart chartType="ColumnChart" :chartData="this.data" :chartOptions="this.options" />
        </div>
     </div>
</template>
<script>
import Vue from 'vue'
import VuePapaParse from 'vue-papa-parse'
import Chart from './card/Chart.vue'
Vue.use(VuePapaParse)

export default {
    name:"uploader",
    data:()=>{
        return{
            myFile:'',
            data:[
                                    // ['Year', 'Sales', 'Expenses', 'Profit'],
                                    // ['2014', 1000, 400, 200],
                                    // ['2015', 1170, 460, 250],
                                    // ['2016', 660, 1120, 300],
                                    // ['2017', 1030, 540, 350]
                                ],
           options:{
                    height:400,
                    explorer: {axis: 'horizontal', keepInBounds: true},
                    backgroundColor: { 
                                fill:'transparent' 
                                },
                                hAxis: {
                                        textStyle: {
                                            color: 'white'
                                        },
                                        titleTextStyle: {
                                            color: 'white'
                                        }
                                    },
                                    vAxis: {
                                        textStyle: {
                                            color: 'white'
                                        },
                                        titleTextStyle: {
                                            color: 'white'
                                        }
                                    },
                                    legend: {
                                        textStyle: {
                                            color: 'white'
                                        },
                                        position:"bottom"
                                    },
                            colors: ["green","yellow","orange"],
                        }
        }
    },
    components:{Chart},
    methods:{
        loadFile(ev){
            const file=ev.target.files[0]
            this.myFile = file
        },
        readData(){
            let comp = this
           this.$papa.parse(this.myFile,{
                 complete:  (results) =>{
                     let properData = results.data.map((row,index)=>{
                            try {
                                if(index!=0)
                                 {
                                     new Date(row[1])

                                }
                            }
                            catch(e){
                                alert(`Date format error at record number :${index+1}` )
                                return
                            }
                            if(index!=0&&(Number(row[3])>Number(row[2]))){
                                alert(`Session is greater than page view at record : ${index+1}`)
                            }
                            return index==0? [row[1],(row[2]),(row[3])]: [new Date(row[1]),Number(row[2]),Number(row[3])]
                         })
                   comp.data=properData
                   console.log(properData);
                }
            })
        }
    }
}
</script>
<style scoped>

</style>


