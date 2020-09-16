<template>
    <div class="container">
        <Header></Header>

        <div class="main-body df" >
            <Uploader />

        <!-- <Card v-for="item in cards" :key="item._id" :title="item.title" :theme="item.theme" :width="item.width" :filters="item.filters"
        :charts="item.charts" :widgets="item.widgets"
        >
        </Card> -->
     </div>
    </div>
    
</template>
<style>
.container{
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    }
.main-body{
    position: absolute;
    top: 44px;
    bottom: 0;
    left: 0;
    right: 0;
    overflow-y: scroll;
     flex-wrap: wrap;
    background: #262626;

}    
</style>
<script>
import Header from './Header.vue'
import Uploader from './Uploader.vue'
export default {
    name:'Container',
    components:{Header,Uploader},
    data:()=>{
        return {
            hello:"world"
                }
            
             }
    
}
</script>

