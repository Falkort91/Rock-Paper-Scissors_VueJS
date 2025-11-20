<script setup>
import TitleGame from './components/TitleGame.vue';
import Result from './components/Result.vue';
import AreaGame from './components/areaGame/AreaGame.vue';
import {reactive} from 'vue';

const resultData=reactive({});
const stockData =(data)=>{
    Object.assign(resultData,data);
}
</script>

<template>

   <section class="container mx-auto text-center mt-40">
        <title-game/>
        <area-game @results="stockData"/>
        <result :data="resultData"><p  class="text-2xl font-semibold mb-4" v-html="resultData.resultSentence"></p></result>
    </section>

</template>

<style scoped>

</style>
