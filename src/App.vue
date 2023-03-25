<template>
    <div class="main">
        <div class="timers">
            <Timer v-for="(item, index) in numTimer" :key="index" v-bind="item"></Timer>

            <div class="timers_add-timer" v-on:click="addTimer()">
                <span></span>
                <span></span>
            </div>
        </div>
    </div>
</template>

<script lang="js">
import Timer from './components/timer.vue';

export default { 
    components: { Timer },
    data() {
    return {
      numTimer: 0,
        };
    },
    methods: {
        addTimer() {
            this.numTimer += 1
        }
    }
}
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
        .timers_add-timer{
            background-color: #696969;
            width: 225px;
            height: 120px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            margin: 22.5px 25px;
            cursor: pointer;
            span{
                position: absolute;
                width: 3px;
                height: 20px;
                background: #9E9E9E;
                &:nth-child(2){
                    transform: rotate(-90deg);
                }
            }
        }
    }
}
</style>
