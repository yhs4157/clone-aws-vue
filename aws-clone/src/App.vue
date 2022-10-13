<template>

  <div class="black-bg" v-if="모달창열렸니" @click=toggle>
    <div class="white-bg" @click.stop="toggle">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
    </div>
  </div>

  <div class="menu">
    <a v-for="(ele, index) in menus" :key="index">{{ele}} </a>
  </div>
  <div v-for="index in 3" :key="index">
    <img :src='pictures[index]'>
    <h4 @click="모달창열렸니 = true">{{products[index]}}</h4>
    <p>{{prices[index]}} 만원</p>
    <button @click=increase(index)>허위매물신고</button> <span>신고수: {{신고수[index]}}</span>
  </div>

  <App></App>

</template>

<script>
import App from "./components/exmaple.vue";

export default {
  name: 'App',
  data(){
    return {
      모달창열렸니: false, 
      menus: ['home', 'shop', 'about'],
      products: ['dummy','역삼동원룸','천호동원룸','마포구원룸'],
      prices: [-1,60, 70, 80],
      신고수: [-1, 0, 0, 0],
      pictures: [
        "dummy", 
        'https://t1.daumcdn.net/cfile/tistory/1128E9114BA1CECE46', 
        'https://t1.daumcdn.net/cfile/tistory/1228E9114BA1CECE47',
        'https://t1.daumcdn.net/cfile/tistory/1428E9114BA1CECF48',
      ]
    }
  },
  methods : {
    increase(index){
      this.신고수[index]++;
    },
    toggle(){
      this.모달창열렸니 = !this.모달창열렸니
    }
  },
  component(){
    App;
  }
}
</script>

<style>
body {
  margin: 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; 
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%; 
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
  margin-bottom: 15px;
}

.menu a {
  color: white;
  padding: 10px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
