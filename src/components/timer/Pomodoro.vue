<template>
  <div>
    <div class="container min-full-height">
      <div class="main-content row">
        <div v-show="state !== 0" class="col-sm-12 col-md-6 col-lg-5">
          <div v-if="!showKittens">
            <img class="img-fluid rounded" :src="chosenWorkout.picture" :alt="chosenWorkout.name">
            <h2 class="title">{{ chosenWorkout.name }}</h2>
            <p class="description">
              {{ chosenWorkout.description }}
            </p>
          </div>
          <div v-if="showKittens">
            <kittens-component></kittens-component>
          </div>
          <div v-if="!showKittens">
            <button type="button" class="button button-primary">Done!</button>
            <button type="button" class="button button-primary">Next</button>
          </div>
          <div class="lazy-section">
            <h4 class="title">Feeling <span class="bold">{{ showKittens ? 'energetic' : 'lazy' }}</span>?</h4>
            <button type="button" class="button button-primary-faded" @click="toggleKittens">{{ showKittens ? showWorkoutsButtonText : showKittensButtonText }}</button>
          </div>
        </div>
        <div class="countdown-holder col-sm-12" v-bind:class="[state !== 0 ? 'col-md-6 col-lg-7' : 'col-md-12']">
          <count-down-timer ref="countdowntimer" @finished="togglePomodoro" :time="time"></count-down-timer>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  import CountDownTimer from './CountDownTimer.vue'
  import KittensComponent from './KittensComponent.vue'

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
        chosenWorkout: {name: 'Pushups', description: 'Do 10 pushups', picture: require('../../assets/images/pushups.png')},
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
      CountDownTimer,
      KittensComponent
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
      },
      toggleKittens () {
        this.showKittens = !this.showKittens
      }
    }
  }
</script>
<style scoped lang="scss">
  @import "../../assets/styles/main";

  .title {
    margin: 10px 0;
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
