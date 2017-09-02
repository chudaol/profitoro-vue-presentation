<template>
  <div id="app" class="reveal">
    <div class="timer">
      <pomodoro></pomodoro>
    </div>
    <workout-component></workout-component>
    <div class="slides">
      <section>
        <h2>Hi, my name is Olga</h2>
        <div>
          <div class="logos row align-items-center">
            <div class="col-6">
              <img src="./assets/optiopay-logo.png" alt="">
            </div>
            <div class="col-6 text-right">
              <img src="./assets/edera_logo.png" alt="">
            </div>
          </div>
        </div>
      </section>
      <section>
        <h2>How I manage time and stay fit with Vue.js</h2>
        <div>
          <tomato></tomato>
        </div>
      </section>
      <section>
        <h2>ProFitOro - part of the book</h2>
        <p><a href="https://goo.gl/bQbwpW">https://goo.gl/bQbwpW</a></p>
        <img src="./assets/images/book_cover.png" alt="book cover">
        <p>Not published yet</p>
      </section>
      <section>
        <h2>Outline</h2>
        <ul>
          <li>How I wrote my first book about Vue.js</li>
          <li>What is ProFitOro</li>
          <li>Vue, Vuex, Nuxt</li>
          <li>Firebase - auth, datastorage, database, hosting</li>
          <li>Jest - snapshot testing</li>
          <li>Trigonometry + SVG + Vue = &hearts;</li>
          <li>CircleCI</li>
        </ul>
      </section>
      <section>
        <h2>How I wrote a book about Vue.js</h2>
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
        <img src="./assets/images/email1.png" alt="first email">
      </section>
      <section>
        <h2>How it all started</h2>
        <p>11/04/2016 12:30</p>
        <img src="./assets/images/email2.png" alt="lol">
      </section>
      <section>
        <h2>How it all started</h2>
        <p>12/04/2016 09:30</p>
        <img src="./assets/images/email3.png" alt="first email">
      </section>
      <section>
        <h2>Family support</h2>
        <img src="./assets/images/review.jpg" alt="Reviews">
      </section>
      <section>
        <h2>What is the book about</h2>
        <ul>
          <li class="fragment">Two applications</li>
          <li class="fragment">Developed from scratch</li>
          <li class="fragment">Going through unit tests and e2e tests</li>
          <li class="fragment">Deployed + CI</li>
        </ul>
      </section>
      <section>
        <h2>Problems</h2>
        <img src="./assets/images/vue2.png" alt="">
      </section>
      <section>
        <h2>Happiness</h2>
        <img src="./assets/images/photowithbook.jpg" alt="">
      </section>
      <section>
        <h2>Surprise</h2>
        <img src="./assets/images/hackernews.jpg" alt="">
      </section>
      <section>
        <h2>Still</h2>
        <p>Writing books? Never ever again!</p>
      </section>
      <section>
        <h2>All of a sudden</h2>
        <img src="./assets/images/email4.png" alt="">
      </section>
      <section>
        <h2>Let's do it!</h2>
        <img src="./assets/images/profitoro_logo.svg" alt="">
      </section>
      <section>
        <h2>What is ProFitOro?</h2>
        <p><a href="https://profitorolife.com/">https://profitorolife.com/</a></p>
        <img class="not-so-big" src="./assets/images/background.png" alt="background">
      </section>
      <section>
        <h2>
          What is ProFitOro?
        </h2>
        <ul>
          <li>Pomodoro timer</li>
          <li>Workouts</li>
        </ul>
      </section>
      <section>
        <img src="./assets/images/workout.png" alt="">
      </section>
      <section>
        <h2>Vue, Vuex, Nuxt</h2>
        <p>Nuxt is awesome</p>
        <div class="left-column fragment">
          <h4>Vue router</h4>
<pre><code data-trim>
//components/Pomodoro.vue
const Pomodoro = {
  template: 'Timer'
}
//components/About.vue
const About = {
  template: 'This is ProFitOro'
}
//router.js
const router = new VueRouter({
  routes: [
    { path: '/pomodoro', component: Pomodoro },
    { path: '/about', component: About }
  ]
})
          </code>
        </pre>
        </div>
        <div class="right-column fragment">
          <h4>Nuxt</h4>
          <pre>
            <code>
//pages/pomodoro.vue
const Pomodoro = {
  template: 'Timer'
}
//pages/about.vue
const About = {
  template: 'This is ProFitOro'
}
            </code>
          </pre>
        </div>
      </section>
      <section>
        <h2>Nuxt - middleware</h2>
        <div class="left-column fragment">
          <pre>
          <code>
//middleware/authenticated.js
export default function ({ store, redirect }) {
  if (!store.getters.isAuthenticated) {
    return redirect('/')
  }
}
          </code>
        </pre>
        </div>
        <div class="right-column fragment">
          <pre>
            <code class="html" data-trim data-noescape>
//pages/workouts.vue
&lt;template&gt;
  workouts
&lt;/template&gt;
&lt;script&gt;
 export default {
   middleware: 'authenticated',
 }
&lt;/script&gt;
&lt;style&gt;
  /*...*/
&lt;/style&gt;
            </code>
          </pre>
        </div>
      </section>
      <section>
        <h2>Firebase</h2>
        <img src="./assets/images/firebase.png" alt="Firebase">
      </section>
      <section>
        <h2>Firebase</h2>
        <ul>
          <li class="fragment">Authentication</li>
          <li class="fragment">Datastorage</li>
          <li class="fragment">Real-time database</li>
          <li class="fragment">Hosting + SSL</li>
        </ul>
        <div class="fragment">&hearts;</div>
      </section>
      <section>
        <h2>Firebase</h2>
        <h3>Auth</h3>
        <p>store/actions.js</p>
        <pre>
          <code>
authenticate ({state, dispatch}, {email, password}) {
  firebaseApp.auth().signInWithEmailAndPassword(email, password)
}
          </code>
        </pre>
      </section>
      <section>
        <h2>Firebase</h2>
        <h3>Auth</h3>
        <p>components/Login.vue</p>
        <pre>
          <code>
&lt;template&gt;
  &lt;input v-model="email" type="email" placeholder="username or email address" /&gt;
  &lt;input v-model="password" type="password" placeholder="password" /&gt;
  &lt;button @click="onAuth">Login!&lt;/button>
&lt;/template>

&lt;script>
  import { mapActions } from 'vuex'

  export default {
    methods: {
      ...mapActions(['authenticate']),
      onAuth () {
        this.authenticate({email: this.email, password: this.password})
      }
    }
  }
&lt;/script&gt;
          </code>
        </pre>
      </section>
      <section>
        <h2>Jest</h2>
        <h3>Snapshot testing FTW</h3>
        <pre>
          <code>
test('login snapshot', () => {
  let $mounted = new Vue({
    template: '&lt;login-page&gt;&lt;/login-page&gt;',
    store: store(),
    components: {
      'login-page': LoginPage
    }
  }).$mount()
  let $html = $mounted.$el.outerHTML
  expect($html).toMatchSnapshot()
})
          </code>
        </pre>
      </section>
      <section>
        <h2>CircleCI</h2>
        <img src="./assets/images/ci.png" alt="CI">
      </section>
      <section>
        <h2>CircleCI</h2>
        <h3>Simple configuration</h3>
        <div class="left-column">
          <img src="./assets/images/workflow.png" alt="">
        </div>
        <div class="right-column">
          <pre>
            <code>
workflows:
  version: 2
  build-and-approval-deploy:
    jobs:
      - build
      - hold:
         type: approval
         requires:
           - build
      - deploy:
          requires:
            - hold
            </code>
          </pre>
        </div>
      </section>
      <section>
        <h2>Timer</h2>
        <p>Just an SVG</p>
        <pre>
          <code>
<div class="center-content">
  &lt;svg class="timer" viewBox="0 0 200 200" preserveAspectRatio="xMinYMin meet" xmlns="http://www.w3.org/2000/svg">
    &lt;circle class="bigCircle" r="100" cx="100" cy="100">&lt;/circle>
    &lt;circle class="smallCircle" r="90" cx="100" cy="100">&lt;/circle>
    &lt;path class="segment" :d="M100,100 L100, 0 A100,100 0 0,0 X, Y z">&lt;/path>
  &lt;/svg>
</div>
          </code>
        </pre>
        <ul>
          <li>M - move to</li>
          <li>L - line to</li>
          <li>A - arc</li>
        </ul>
      </section>
      <section>
        <h2>Timer</h2>
        <h3>Find X and Y</h3>
        <pre>
          <code>
&lt;template>
  &lt;svg class="timer">
    &lt;circle class="bigCircle" r="100" cx="100" cy="100">&lt;/circle>
    &lt;circle class="smallCircle" r="90" cx="100" cy="100">&lt;/circle>
    &lt;path class="segment" :d="path">&lt;/path>
  &lt;/svg>
&lt;/template>
&lt;script>
  function calcEndPoint (angle) {
    let x, y

    x = 100 - 100 * Math.sin(Math.PI * angle / 180)
    y = 100 - 100 * Math.cos(Math.PI * angle / 180)

    return {
      x, y
    }
  }

  function calcPath (angle) {
    let d
    let {x, y} = calcEndPoint(angle)
    if (angle <= 180) {
      d = `M100,100 L100, 0 A100,100 0 0,0 ${x}, ${y} z`
    } else {
      d = `M100,100  L100, 0 A100,100 0 0,0 100, 200 A100,100 0 0,0 ${x}, ${y} z`
    }
    return d
  }
  export default {
    props: ['angle'],
    computed: {
      path () {
        return calcPath(this.angle)
      }
    }
  }
&lt;/script>
          </code>
        </pre>
      </section>
      <section>
        <h2>Timer</h2>
        <h3>Angle calculation</h3>
        <p>Set timeout and recalculate time property</p>
        <p><strong>angle</strong> is a computed property</p>
        <pre>
          <code>
angle () {
  return 360 - (360 / this.time * this.timestamp)
},
          </code>
        </pre>
      </section>
      <section>
        <h2>Was it worth it?</h2>
        <ul>
          <li>I've learned a lot</li>
          <li>I have my second book</li>
          <li>I have my ProFitOro and I use it</li>
          <li>Big win! <span class="pink">&hearts;</span></li>
        </ul>
      </section>
      <section>
        <h2>Conclusion</h2>
        <p class="fragment">Do not hesitate</p>
        <p class="fragment">Just do it <span class="big-text pink">&hearts;</span></p>
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
      hljs.initHighlightingOnLoad();
    }
  }
</script>

<style scoped lang="scss">
  img.not-so-big {
    max-height: 70vh!important;
  }
  .logos {
    width: 80%;
    margin: auto;
  }
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
