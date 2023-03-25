<template>
    <div class="main">
        <div class="timers">
            <Timer/>
        </div>
    </div>
</template>

<script lang="js">
import Timer from './components/timer.vue';

export default { 
    components: { Timer } 
    
    };
</script>

<style lang="scss">
@font-face {
    font-family: 'GothamPro';
    src: url('./fonts/GothamPro.woff2') format('woff');
    font-weight: normal;
    font-style: normal;
}
body{
    background-color:  #353638;
}

.main{
    display: flex;
    justify-content: center;
    align-items: center;
    .timers{
        max-width: 850px;
        padding-top: 48px;
        display: flex;
        flex-wrap: wrap;
        @media (max-width: 840px){
            max-width: 550px;
        }
        @media (max-width: 565px){
            max-width: 275px;
        }
    }
}
</style>
