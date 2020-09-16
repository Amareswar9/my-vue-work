<template>
    <div class="header df">
        <div class="h-left">
            <span class="mdi mdi-midi-port" style="color:#e08640" ></span>

            DASHBOARD
        </div>
        <div class="h-controls">
              <span class="mdi mdi-bell" style="color:#e08640" ></span>
           
             <span class="mdi mdi-face" style="color:#e08640" ></span>
           
        </div>
    </div>
</template>
<style scoped>
    .header{
        height:44px;
        background:#0F0F0F;
        color:white;
        font-size: 18px;
        font-weight: bold;
            align-items: center;
    justify-content: space-between;
    }
    .h-left{
        padding: 0 16px;
    }
    .h-controls{
        padding: 0 16px;
    }
    .h-controls span{
        margin-left: 12px;
    }
</style>
<script>
export default {
    name:'Header'
}
</script>

