<template>
  <div id="app">
    <h1 v-html="message"
    v-bind:class="classObject"></h1>
    <img alt="Vue logo" src="./assets/logo.png">
    <PracticeIndex></PracticeIndex>
    <ChildComponent
    v-show='isShow'>
    <template #head>
      <p>head slot</p>
    </template> 
    <template #default>
      <p>main slot</p>
      <p>main slot2</p>
    </template>
    <template #foot>
      <p>foot slot</p>
    </template>
    </ChildComponent>
    <hr>
      <p v-if='id === 1'>1</p>
      <p v-else-if='id === 2'>2</p>
      <p v-else>other</p>
    <hr>
    <ul>
      <template v-for="item in items">
        <ChildComponent :key="item.id">
          <span>slot content</span>
        </ChildComponent>
      </template>
      <hr>
      <button @click="incrementCount">CLICK</button>
       <P>{{ count }}回押した</P> 
       <hr>
       <input type="text" v-model="inputText">
       <p>computed: {{ getUpperCaseText }}</p>
       <p>methods: {{ showUpperCaseText() }}</p>
    </ul> 
  </div>
</template>

<script>
import PracticeIndex from './components/PracticeIndex'
import ChildComponent from './components/ChildComponent';


export default {
  name: 'App',
  components: {
    PracticeIndex,
    ChildComponent,
  },
  data() {
    return{
      message:  '<span>Hello Vue</span>',
      isShow: true,
      id: 2,
      count: 0,
      inputText: '',
      classObject: {
      'is-green': true,
      },
    items: [
      {
        id: 1,
        title: '1番目のリスト',
      },
      {
        id: 2,
        title: '２番目のリスト'
      },
      {
        id: 3,
        title: '3番目のリスト'
      }
    ],
   }
  },
   methods: {
      incrementCount(){
        this.count++;
    },
    showUpperCaseText() {
    const upperCaseText = this.inputText.toUpperCase();
    console.log(`method: ${upperCaseText}`);
    return upperCaseText;
    }
    }, 
    computed: {
      getUpperCaseText() {
        const upperCaseText = this.inputText.toUpperCase();
        console.log(`computed: ${upperCaseText}`);
        return upperCaseText;
      }
    },
};

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.is-green {
  color: green;
}
hr {
  margin: 16px 0;
}
</style>
