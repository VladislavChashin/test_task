<template>
    <div class="timers_timer-wrap">
        <div class="timer-wrap_time">
            <p v-if="hours != 0">{{hours}} : {{minutes}} : {{seconds}}</p>
            <p v-else-if="minutes != 0">{{minutes}} : {{seconds}}</p>
            <p v-else>{{seconds}}</p>
        </div>
        <div class="timer-wrap_interaction">
            <p v-on:click="start_stopTimer()" v-if="!state"><img src='./img/start.svg' alt=""></p>
            <p v-on:click="start_stopTimer()" v-else><img src='./img/stop.svg' alt=""></p>
            <p v-on:click="beforeDestroy()"><img src='./img/destoy.svg' alt=""></p>
        </div>
    </div>
</template>

<script lang="js">

export default {
    
    data() {
    return {
      hours: 59,
      minutes: 59,
      seconds: 50,
      state: false,
      timerId: null,
        };
    },
    methods: {
        start_stopTimer() {
            if (this.state == false){
                this.state = true;
                this.timerId = setInterval(() =>{
                if (this.seconds == 59 ){
                    if (this.minutes == 59){ 
                        if (this.hours == 100){
                            clearInterval(this.timerId);
                        }else{
                            this.hours += 1
                            this.minutes = 0
                        }
                    }else{
                        this.minutes += 1
                        this.seconds = 0
                    }
                }else{
                    this.seconds += 1
                }

                }, 1000)
            }else{
                clearInterval(this.timerId);
                this.state = false;
            }
            
        },
        beforeDestroy() {
            clearInterval(this.timerId);
            this.seconds = 0;
            this.minutes = 0; 
            this.hours = 0;
        }
    }
}
</script>

<style lang="scss">
    .timers_timer-wrap{
        background-color: #696969;
        width: 225px;
        height: 120px;
        display: flex;
        flex-direction: column;
        align-items: center;
        .timer-wrap_time{
            p{
                font-family: 'Gotham Pro';
                font-weight: 400;
                font-size: 22px;
                line-height: 21px;
                color: #9E9E9E;
            }
        }
        .timer-wrap_interaction{
            display: flex;
        }
    }
</style>