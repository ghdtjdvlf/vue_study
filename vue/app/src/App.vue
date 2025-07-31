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
  width: 100%;
  background: #fff;
  border-radius: 8px;
  padding: 20px;
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding-left: 10px;
}

.list {
  text-align: center;
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

  <div class="black-bg">
    <div class="white-bg">
      <h4>상세페이지입니다</h4>
      <p>상세페이지내용</p>
    </div>
  </div>

  <div v-for="(a, i) in products" :key="i">
    <img src="./assets/images/room0.jpg" class="room-img" alt="" />
    <h4>{{ a }}</h4>
    <p>{{ price1[i] }}만원</p>
    <button @click="report[i]++">허위매물신고</button>
    <span>신고 수 : {{ report[i] }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      nav: ["Home", "Products", "About", "About", "About", "About"],
      price1: [60, 70, 80],
      products: ["역삼동 원룸", "천호동 원룸", "마포구원룸"],
      report: [0, 0, 0],
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
