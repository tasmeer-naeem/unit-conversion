<template>
    <div class="container">
    <temp-converter/>
    <br/>
    <br/>
    <volume-converter/>
    <div>       
    </div>
    </div>
</template>


<script>
import tempConverter from '../components/tempConverter.vue'
import volumeConverter from '../components/volumeConverter.vue'
export default {
        name:'dashboardPage' ,
    components: { 
    tempConverter  ,
    volumeConverter
    },
}
</script>

<style scoped>
.container{
    color:black;
    font-weight:bold;
}
</style>