<template>

     <select class="filter-sel">
        <option v-for="f in filters" :key="f" value="f">{{f}}</option>
    </select> 
</template>
<style scoped>
    .filter-sel{
        background: transparent;
    color: #ebe6de;
    border: 0;
    border-bottom: 1px solid #ebe6de;
    }
</style>
<script>
export default {
    name:"FilterComponent",
    props:["filters"],
    data(){
        return{

        }
    }
}
</script>

