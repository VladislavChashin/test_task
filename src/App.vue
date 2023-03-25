<template>
    <div class="main">
        <div class="timers">
            <Timer/>
        </div>
    </div>
</template>

<script lang="js">
import Timer from './components/timer.vue';

export default { components: { Timer } };
</script>

<style lang="scss">
body{
    background-color:  #353638;
}
#app{
    width: 100%;
    height: 100%;
    margin: 0 auto;
}
.main{
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    .timers{
        width: 775px;
        min-height: 495px;
    }
}
</style>
