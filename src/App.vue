<template>
  <div id="app" class="reveal">
    <div class="timer">
      <pomodoro></pomodoro>
    </div>
    <workout-component></workout-component>
    <div class="slides">
      <section>
        <h1>Hi, my name is Olga</h1>
        <div>
          <div class="logos row align-items-center">
            <div class="col-6">
              <img src="./assets/optiopay-logo.svg" alt="">
            </div>
            <div class="col-6">
              <img src="./assets/edera_logo.png" alt="">
            </div>
          </div>
        </div>
        <aside class="notes">
          Oh hey, these are some notes. They'll be hidden in your presentation, but you can see them if you open the speaker notes window (hit 's' on your keyboard).
        </aside>
      </section>
      <section>
        <h1>How I manage time and stay fit with Vue.js</h1>
        <div>
          <tomato></tomato>
        </div>
      </section>
      <section>
        <h1>How I wrote a book about Vue.js</h1>
      </section>
      <section>
        <h2>Learning Vue.js 2</h2>
        <a href="https://goo.gl/1ayuof">https://goo.gl/1ayuof</a>
      </section>
      <section>
        <h2>I am not any Vue.js Guru</h2>
      </section>
      <section>
        <h2>How it all started</h2>
        <p>11/04/2016 11:30</p>
        <img src="img/email1.png" alt="first email">
      </section>
    </div>
  </div>
</template>

<script>
  import Reveal from 'reveal'
  import Clock from './components/Clock.vue'
  import Tomato from './components/Tomato.vue'
  import Pomodoro from './components/timer/Pomodoro.vue'
  import WorkoutComponent from './components/WorkoutComponent.vue'
  export default {
    name: 'app',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    },
    components: {
      Pomodoro, Tomato, WorkoutComponent
    },
    mounted () {
      Reveal.initialize({
        controls: true,
        progress: true,
        history: true,
        center: true,
        // default/cube/page/concave/zoom/linear/fade/none
        transition: 'default'
      })
    }
  }
</script>

<style scoped lang="scss">
  .logos img {
    padding: 20px;
    background: transparent;
    border: none;
    box-shadow: none;
  }
  .timer {
    padding-top: 15px;
    padding-left: 15px;
    width: 10%;
  }
  .logo {
    display: inline;
    max-width: 30%;
    background-color: white;
  }
</style>
