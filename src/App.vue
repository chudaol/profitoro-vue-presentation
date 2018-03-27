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
        <h2>How I manage time and try to stay fit with Vue.js</h2>
        <div>
          <tomato></tomato>
        </div>
      </section>
      <section>
        <h2>Outline</h2>
        <ul>
          <li>What is ProFitOro</li>
          <li>Vue and Nuxt - components, data binding and routing</li>
          <li>Firebase - auth, datastorage, database, hosting</li>
          <li>Jest - snapshot testing</li>
          <li>Kittens</li>
          <li>Why I wrote books about Vue.js?</li>
          <li>Knowledge Sharing</li>
        </ul>
      </section>
      <section>
        <h1>What is ProFitOro &#x2753;</h1>
      </section>
      <section>
        <p><a href="https://goo.gl/bQbwpW">https://goo.gl/bQbwpW</a></p>
        <img style="height: 55vh" src="./assets/images/book_cover.png" alt="book cover">
        <p>Published in december 2017</p>
      </section>
      <section>
        <p><a href="https://profitorolife.com/">https://profitorolife.com/</a></p>
        <img class="not-so-big" src="./assets/images/background.png" alt="background">
      </section>
      <section>
          <p class="very-big-text"><span class="nice-pink">P</span>omod<span class="nice-pink">oro</span> &#x1F345;  &#x23F3; management technique</p>
          <p class="very-big-text fragment"><span class="very-very-big-text nice-pink">+</span></p>
          <p class="very-big-text fragment">Office <span class="nice-pink">fit</span>ness workouts &#x1F4AA;</p>
          <p class="very-big-text fragment"><span class="very-very-big-text big-text nice-pink">=</span></p>
          <p class="very-big-text fragment"><span class="big-text nice-pink">Profit &#x1F4B0;</span></p>
      </section>
      <section>
        <img src="./assets/images/screenshot1.png" alt="Screenshot1">
      </section>
      <section>
        <img src="./assets/images/screenshot2.png" alt="Screenshot1">
      </section>
      <section>
        <img src="./assets/images/screenshot3.png" alt="Screenshot1">
      </section>
      <section>
        <img src="./assets/images/screenshot4.png" alt="Screenshot1">
      </section>
      <section>
        <h1>
          Vue Components
        </h1>
        <h1>&#x1F529; &#x1F528; &#x1F527;</h1>
      </section>
      <section>
        <p class="fragment">File with .vue extension</p>
        <pre class="fragment">
          <code>
&lt;template>
  // some markup
&lt;/template>

&lt;script>
  // some js
&lt;/script>

&lt;style scoped>
  // some css
&lt;/style>
          </code>
        </pre>
      </section>
      <section>
        <div style="display: flex; align-items: center">
          <div class="left-column">
          <pre>
          <code v-pre>
&lt;template>
  &lt;h5>Hello {{ name }}&lt;/h5>
&lt;/template>
&lt;script>
  export default {
    data () {
      return {
        name: 'Olga'
      }
    }
  }
&lt;/script>
&lt;style scoped>
  h5 {
    color: #317a80;
    background: ghostwhite;
  }
&lt;/style>
          </code>
        </pre>
          </div>
          <div class="right-column">
            <hello></hello>
          </div>
        </div>
      </section>
      <section>
        <h1>Vue - two way data binding</h1>
        <h1>&#x21A9; &#x21AA; &#x1F389; &#x1F47B;</h1>
      </section>
      <section>
        <div style="display: flex; align-items: center">
          <div class="left-column">
          <pre>
          <code v-pre>
&lt;template>
  &lt;div>
    &lt;h5>Hello {{ name }}&lt;/h5>
    &lt;input type="text" v-model="name">
  &lt;/div>
&lt;/template>
&lt;script>
  export default {
    data () {
      return {
        name: 'Olga'
      }
    }
  }
&lt;/script>
&lt;style scoped>
  h5 {
    color: #317a80;
    background: ghostwhite;
  }
&lt;/style>
          </code>
        </pre>
          </div>
          <div class="right-column">
            <hello2></hello2>
          </div>
        </div>
      </section>
      <section>
        <h1>Data Binding + SVG + trigonometry = <span class="nice-pink">&hearts;</span></h1>
      </section>
      <section>
        <p>Timer - just an SVG</p>
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
        <p>
          <em>
            x = 100 – b
          </em>
        </p>
        <p>
          <em>
            y = 100 – a
          </em>
        </p>
        <img class="not-so-big" src="./assets/images/trigonometry.png" alt="trigonometry">
      </section>
      <section>
        <p>
          <em>
            x = 100 – 100 * sin&alpha;
          </em>
        </p>
        <p>
          <em>
            y = 100 – 100 * cos&alpha;
          </em>
        </p>
        <img class="not-so-big" src="./assets/images/trigonometry.png" alt="trigonometry">
      </section>
      <section>
        <h2>Svg Circle component</h2>
        <p><em>SvgCircle.vue</em></p>
        <pre>
          <code>
&lt;template>
  &lt;svg class="timer" viewBox="0 0 200 200" preserveAspectRatio="xMinYMin meet" xmlns="http://www.w3.org/2000/svg">
    &lt;circle class="bigCircle" r="100" cx="100" cy="100">&lt;/circle>
    &lt;circle class="smallCircle" r="90" cx="100" cy="100">&lt;/circle>
    &lt;path class="segment" :d="path">&lt;/path>
  &lt;/svg>
&lt;/template>
&lt;script>
  export default {
    props: ['angle'],
    computed: {
      path () {
        let x = 100 - 100 * Math.sin(Math.PI * this.angle / 180)
        let y = 100 - 100 * Math.cos(Math.PI * this.angle / 180)

        return this.angle <= 180 ? `M100,100 L100, 0 A100,100 0 0,0 ${x}, ${y} z` : `M100,100  L100, 0 A100,100 0 0,0 100, 200 A100,100 0 0,0 ${x}, ${y} z`
      }
    }
  }
&lt;/script>
          </code>
        </pre>
      </section>
      <section>
        <div style="display:flex">
          <div style="display:flex; flex-direction: column">
            <SvgCircle angle="90" />
            <p><small>&lt;SvgCircle angle="90" /></small></p>
          </div>
          <div style="display:flex; flex-direction: column">
            <SvgCircle angle="45" />
            <p><small>&lt;SvgCircle angle="45" /></small></p>
          </div>
          <div style="display:flex; flex-direction: column">
            <SvgCircle angle="273" />
            <p><small>&lt;SvgCircle angle="273" /></small></p>
          </div>
        </div>
      </section>
      <section>
        <h4>Updating the angle with time</h4>
        <iframe width="100%" height="600" src="//jsfiddle.net/chudaol/ak851ecj/6/embedded/js,html,css,result/dark/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
      </section>
      <section>
        <h1>&#x1F638; &#x1F63A; &#x1F63B; &#x1F63C;</h1>
      </section>
      <section>
        <h3>Kitten Component</h3>
        <pre>
          <code>
&lt;template>
  &lt;div class="well kittens text-center">
    &lt;img :src="catimgsrc" />
  &lt;/div>
&lt;/template>

&lt;script>
  export default {
    data () {
      return {
        timestamp: Date.now()
      }
    },
    computed: {
      catimgsrc () {
        return 'http://thecatapi.com/api/images/get?size=med&ts=' + this.timestamp
      }
    },
    created () {
      const INTERVAL = 10000
      setInterval(() => {
        this.timestamp = Date.now()
      }, INTERVAL)
    }
  }
/script>
          </code>
        </pre>
      </section>
      <section>
        <h4>Kitten Component</h4>
        <iframe width="100%" height="600" src="//jsfiddle.net/chudaol/odL9okk8/1/embedded/html,js,result/dark/" allowfullscreen=true frameborder="0"></iframe>
      </section>
      <section>
        <h1>Nuxt</h1>
        <h1>&#x2728; &#x1F680; &#x1F36D;</h1>
      </section>
      <section>
        <p>Nuxt is a template for creating Vue application</p>
        <p class="nice-pink">vue init nuxt my-awesome-project</p>

      </section>
      <section>
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
        <h2>Nuxt - a lot more</h2>
        <ul>
          <li>Server-side rendering</li>
          <li>Code splitting</li>
          <li>Sexy configuration</li>
        </ul>
        <pre>
          <code>
module.exports = {
  /*
  ** Headers of the page
  */
  head: {
    title: 'ProFitOro',
    meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      { hid: 'description', name: 'description', content: 'ProFitOro is a Pomodoro timer implementation combined with office workouts. Take breaks during work. Exercise during breaks ' },
      { hid: 'keywords', name: 'keywords', content: 'Pomodoro, workouts, fit, time management, office workouts, pomodoro technique' },
      { hid: 'image', property: 'og:image', name: 'og:image', content: 'https://firebasestorage.googleapis.com/v0/b/profitoro-ad0f0.appspot.com/o/assets%2Fsharing.png?alt=media&token=d8687d98-24a7-4a8a-b0c4-06a39b127443' },
      { hid: 'url', property: 'og:url', name: 'og:url', content: 'https://www.profitorolife.com' },
      { hid: 'title', property: 'og:title', name: 'og:title', content: 'ProFitOro' },
      { hid: 'ogdescription', property: 'og:description', name: 'og:description', content: 'ProFitOro is a Pomodoro timer implementation combined with office workouts. Take breaks during work. Exercise during breaks ' }
    ],
    link: [
      { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' },
      { rel: 'stylesheet', type: 'stylesheet', lang: 'scss', href: '~/assets/styles/main.scss' }
    ],
    script: [
      { type: 'text/javascript', src: '/jquery.js' },
      { type: 'text/javascript', src: '/tether.js' },
      { type: 'text/javascript', src: '/bootstrap.js' }
    ]
  },
  css: [
    '~static/bootstrap.css',
    '~static/main.css'
  ],
  /*
  ** Customize the progress-bar color
  */
  loading: '~/components/loading.vue',
  /*
  ** Build configuration
  */
  build: {
    /*
    ** Run ESLINT on save
    */
    extend (config, ctx) {
      if (ctx.isClient) {
        config.module.rules.push({
          enforce: 'pre',
          test: /\.(js|vue)$/,
          loader: 'eslint-loader',
          exclude: /(node_modules)/
        })
      }
    }
  }
}
          </code>
        </pre>
      </section>
      <section>
        <h1>Firebase</h1>
        <h1>&#x1F308; &#x1F525; &#x1F33B;</h1>
      </section>
      <section>
        <img src="./assets/images/firebase.png" alt="Firebase">
      </section>
      <section>
        <h2>&#x1F3B0;</h2>
        <ul>
          <li class="fragment">Authentication</li>
          <li class="fragment">Datastorage</li>
          <li class="fragment">Real-time database</li>
          <li class="fragment">Hosting + SSL</li>
        </ul>
        <div class="fragment">&hearts;</div>
      </section>
      <section>
        <h1>Firebase - authentication</h1>
        <h1>&#x1F510;</h1>
      </section>
      <section>
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
        <h1>Firebase - realtime database</h1>
        <h1>&#x1F525; &#x1F680;</h1>
      </section>
      <section>
        <div class="left-column fragment">
          <p>Obtain database reference</p>
          <pre>
          <code>
let db = firebaseApp.database()
let configRef = db.ref(`/configuration/${user.uid}`)
          </code>
        </pre>
        </div>
        <div class="right-column fragment">
          <p>Update database</p>
          <pre>
           <code>
// store/actions.js
setWorkingPomodoro () {
  configRef.update({workingPomodoro: 20})
}
          </code>
        </pre>
        </div>
      </section>
      <section>
        <h3>Bind DB reference to the Vuex state</h3>
        <h3>Vuexfire plugin</h3>
        <pre>
          <code>
// state
const state = {
  config: {}
}

// actions
import firebaseAction from 'vuexfire'

bindConfig: firebaseAction(({bindFirebaseRef}) => {
  bindFirebaseRef('config', configRef)
})
        </code>
      </pre>
      </section>
      <section>
        <h3>Using inside the component</h3>
        <pre>
          <code>
&lt;template>
  &lt;div class="container">
    &lt;input type="text" :value="config.workingPomodoro" @change="setWorkingPomodoro">
  &lt;/div>
&lt;/template>
&lt;script>
  import { mapState, mapActions } from 'vuex'
  export default {
    computed: {
      ...mapState({
        config
      })
    },
    methods: {
      ...mapActions(['setWorkingPomodoro'])
    }
  }
&lt;/script>
          </code>
        </pre>
      </section>
      <section>
        <h3>Result:</h3>
        <video class="screencast" controls src="dist/screencast.mov"></video>
      </section>
      <section>
        <h1>Jest</h1>
        <div class="logos">
          <img src="https://facebook.github.io/jest/img/jest-outline.svg" alt="Jest">
        </div>
      </section>
      <section>
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
        <h1>BONUS! &#x1F4A1;</h1>
      </section>
      <section>
        <h2>BONUS! &hearts;</h2>
        <p><a href="https://profitorolife.com/bibi/">https://profitorolife.com/bibi/</a></p>
      </section>
      <section>
        <img src="./assets/images/cat1.png" alt="cat">
      </section>
      <section>
        <img src="./assets/images/cat2.png" alt="cat">
      </section>
      <section>
        <img src="./assets/images/cat3.png" alt="cat">
      </section>
      <section>
        <img src="./assets/images/cat4.png" alt="cat">
      </section>
      <section>
        <img src="./assets/images/cat5.png" alt="cat">
      </section>
      <section>
        <h1>How I wrote a book about Vue.js</h1>
        <h1>&#x1F481; &#x1F4DD;	&#x1F4D6;</h1>
      </section>
      <section>
        <h2>Learning Vue.js 2</h2>
        <a href="https://goo.gl/1ayuof">https://goo.gl/1ayuof</a>
      </section>
      <section>
        <h1>I am not any Vue.js Guru</h1>
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
        <h2>&#x1F624;</h2>
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
        <h1>Was it worth it?</h1>
      </section>
      <section>
        <h2>Of course it was!</h2>
        <img src="./assets/images/two_books.jpg" alt="">
      </section>
      <section>
        <h2>Of course it was!</h2>
        <ul>
          <li class="fragment">I've learned a lot &#x1F393;</li>
          <li class="fragment">I have 2 books &#x270C;</li>
          <li class="fragment">I have my ProFitOro and I use it &#x1F4AA;</li>
          <li class="fragment">I shared my knowledge with people &#x1F44F;</li>
        </ul>
        <h2 class="fragment">&hearts;</h2>
      </section>
      <section>
        <h1>Knowledge sharing is a big win</h1>
        <h1>&#x1F393; &#x1F49E;</h1>
      </section>
      <section>
        <p><a href="https://ed-era.com/">https://ed-era.com/</a></p>
        <img class="not-so-big" src="./assets/images/edera1.png" alt="EdEra">
      </section>
      <section>
        <p><a href="http://blog.ed-era.com/">http://blog.ed-era.com/</a></p>
        <img class="not-so-big" src="./assets/images/edera2.png" alt="EdEra">
      </section>
      <section>
        <p class="fragment">Do not hesitate</p>
        <p class="fragment">Just do it <span class="big-text pink">&#x2764;</span></p>
      </section>
      <section>
        <h1>Questions?</h1>
        <img src="./assets/images/questions.jpg" alt="questions">
      </section>
      <section>
        <h1>Thank you</h1>
        <h2>&#x1F64C</h2>
        <img src="./assets/images/cat6.png" alt="cat">
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
  import Hello from './components/Hello.vue'
  import Hello2 from './components/Hello2.vue'
  import SvgCircle from './components/timer/SvgCircleSector.vue'
  export default {
    name: 'app',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    },
    components: {
      Pomodoro, Tomato, WorkoutComponent, Hello, Hello2, SvgCircle
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
  .very-big-text {
    font-size: 2em;
    font-weight: 600;
  }
  .very-very-big-text {
    font-size: 2.5em;
    font-weight: 900;
  }
  video.screencast {
    height: 70vh;
  }
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
