<template>

  <div class="black-bg" v-if="모달창열림 == true"> 
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열림 = false">닫기</button>
    </div>
  </div>


  <div class="menu">
    <a v-for="(a,i) in 메뉴들" :key="i"> {{i}} {{a}} </a>
  </div>
  <hr>
  
  <div v-for="(a,i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img">
    <h4 @click="모달창열림 = true" class="sul">{{원룸들[i].title}} </h4>
    <p>{{원룸들[i].price}}원 </p>
    <button @click="구독수[i]++">구독신청</button> <span>구독수 : {{구독수[i]}} </span>
  </div>
</template>

<script>

import data from './assets/data.js';


export default {
  name: 'App',
  data(){
    return {
      원룸들 : data,
      모달창열림 : false,
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      구독수 : [0,0,0,0,0,0],
    }
  },
  methods : {

  },
  components: {
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
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; 
  background: white;
  border-radius: 8px;
  padding: 20px;
}
.sul {
  width: 100%;
}
.room-img {
  width: 30%;
  margin-top: 10px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
