<template>
    <div class="w-outer">
        <div class="w-title">
            {{title}}
        </div>
        <div class="w-content" :class="alertType">
            {{content}}
        </div>   
        </div>
</template>
<style scoped>
    .w-outer{
            margin: 12px 18px;
    background: #323232;
    padding: 6px 12px;
    border-radius: 4px;
    }
    .w-title{
            font-size: 12px;
            color:#979595
    }
    .w-content{
        font-size: 18px;
    font-weight: bold;
    color: #b4b3b3;
    }
    .danger{
        color:#ba2121
    }
    .warning{
        color:#bcbc51
    }
</style>

<script>
export default {
    name:"widget1",
    props:["title","content","alertType"]
}
</script>

