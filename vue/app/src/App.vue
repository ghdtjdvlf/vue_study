<style>
body {
  margin: 0;
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
  width: 30vw;
  margin: 0 auto;
  background: #fff;
  border-radius: 8px;
  padding: 20px;
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
  position: fixed;
  width: 100%;
}

.menu a {
  color: white;
  padding-left: 10px;
}

.list {
  text-align: center;
  width: 400px;
  margin: auto;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>

<template>
  <div class="menu">
    <a v-for="(a, i) in nav" :key="i">{{ a }}</a>
  </div>

  <div class="black-bg" v-if="모달창 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" alt="" class="room-img" />
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].price }}</p>
      <p>{{ 원룸들[누른거].content }}</p>
      <p></p>
      <button @click="모달창 = false">닫기</button>
    </div>
  </div>

  <div v-for="(a, i) in 원룸들" :key="i" class="list">
    <img
      :src="원룸들[i].image"
      class="room-img"
      @click="
        모달창 = true;
        누른거 = i;
      "
    />
    <h4>{{ 원룸들[i].title }}</h4>
    <p>{{ 원룸들[i].price }}원</p>
  </div>
</template>

<script>
import room from "./data/data";
// import {apple,apple1} from "./data/data";

export default {
  name: "App",
  data() {
    return {
      원룸들: room,
      누른거: 0,
      nav: ["Home", "Products", "About", "About", "About", "About"],
      price1: [60, 70, 80],
      products: ["역삼동 원룸", "천호동 원룸", "마포구원룸"],
      report: [0, 0, 0],
      모달창: false,
    };
  },
  methods: {
    increase() {
      this.report[i]++;
    },
  },
};
</script>

<style></style>
