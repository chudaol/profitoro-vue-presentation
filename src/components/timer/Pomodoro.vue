<template>
  <div>
    <div class="container">
      <div class="main-content">
        <div v-show="state !== 0">
          <div class="text-center" v-if="!showKittens">
            <img data-toggle="modal" data-target="#workoutModal" class="img-fluid rounded" :src="chosenWorkout.picture" :alt="chosenWorkout.name">
            <h2 class="title">{{ chosenWorkout.name }}</h2>
          </div>
        </div>
        <div class="countdown-holder">
          <count-down-timer ref="countdowntimer" @finished="togglePomodoro" :time="time"></count-down-timer>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  import CountDownTimer from './CountDownTimer.vue'

  const STATE = {
    WORKING: 0,
    SHORT_BREAK: 1,
    LONG_BREAK: 2
  }
  export default {
    data () {
      return {
        config: {
          workingPomodoro: 25,
          shortBreak: 5,
          longBreak: 10
        },
        state: STATE.WORKING,
        pomodoros: 0,
        chosenWorkout: {name: 'Squats', description: 'Do 10 squats', picture: require('../../assets/images/squats.jpg')},
        showKittens: false,
        showKittensButtonText: 'Show me some kittens!',
        showWorkoutsButtonText: 'I wanna exercise!'
      }
    },
    computed: {
      time () {
        let minutes

        switch (this.state) {
          case STATE.WORKING:
            minutes = this.config.workingPomodoro
            break
          case STATE.SHORT_BREAK:
            minutes = this.config.shortBreak
            break
          case STATE.LONG_BREAK:
            minutes = this.config.longBreak
            break
          default:
            minutes = this.config.workingPomodoro
            break
        }

        return minutes * 60
      }
    },
    components: {
      CountDownTimer
    },
    methods: {
      togglePomodoro () {
        switch (this.state) {
          case STATE.WORKING:
            // we have switched to the break state, increase the number of pomodoros and choose between long and short break
            this.pomodoros ++
            this.state = this.pomodoros % 3 === 0 ? STATE.LONG_BREAK : STATE.SHORT_BREAK
            alert('Time for exercise!')
            break
          default:
            // time to work!
            this.state = STATE.WORKING
            alert('Time to work!')
            break
        }
        this.$refs.countdowntimer.start()
      }
    }
  }
</script>
<style scoped lang="scss">
  @import "../../assets/styles/main";

  .title {
    margin: 10px 0;
    text-align: center;
  }
  .description {
    margin: 20px 0;
    color: #999;
  }
  .button-primary {
    width: 47.5%;
    margin: 0;

    &:first-of-type {
      margin-right: 5%;
      padding: 0;
      float: left;
    }
  }
  .lazy-section {
    margin-top: 40px;

    .title {
      font-size: $font-size-medium;
    }
  }
</style>
