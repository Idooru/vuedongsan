<template>
  <div id="black-bg" v-if="isModalOpened === true">
    <div id="white-bg">
      <button @click="closeModal">X</button>
    </div>
  </div>
  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }} </a>
  </div>
  <h1 class="title">원룸샵</h1>
  <div id="products">
    <div v-for="(roomInfo, idx) in roomInfos" :key="(roomInfo, idx)">
      <img :src="roomInfos[idx].image" class="room-image" />
      <h3 @click="openModal(idx)">{{ roomInfos[idx].title }}</h3>
      <p>{{ roomInfos[idx].price }} 원</p>
      <p>{{ roomInfo.content }}</p>
      <div class="report">
        <button @click="increaseReportCount(idx)">허위매몰신고</button>
        <span>신고수 : {{ roomInfos[idx].countOfReport }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import roomInfos from "./data.js";

export default {
  name: "App",
  data() {
    return {
      roomInfos,
      isModalOpened: false,
      menus: ["Home", "Product", "About"],
    };
  },
  methods: {
    increaseReportCount(idx) {
      this.roomInfos[idx].countOfReport++;
    },
    openModal(idx) {
      this.isModalOpened = true;

      const detailPageTitle = document.createElement("h3");
      const detailPageContents = document.createElement("p");

      detailPageTitle.innerText = this.roomInfos[idx].title;
      detailPageContents.innerText = this.roomInfos[idx].content;

      console.log(detailPageTitle.innerText);
      console.log(detailPageContents.innerText);

      const whiteBG = document.querySelector("#white-bg");
      console.log(whiteBG);
      // whiteBG.appendChild(detailPageTitle);
      // whiteBG.appendChild(detailPageContents);
    },
    closeModal() {
      this.isModalOpened = false;
    },
  },
  components: {},
};
</script>

<style>
body {
  margin: 0px;
}

div {
  box-sizing: border-box;
}

#black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding-top: 70px;
  padding-bottom: 20px;
  padding-left: 120px;
  padding-right: 120px;
}

#white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

#white-bg > button {
  position: absolute;
  top: 70px;
  right: 140px;
  color: red;
  font-weight: 650;
  border: none;
  background-color: rgb(218, 218, 218);
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 26px;
  padding-right: 26px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #1567b9;
}

.title {
  color: crimson;
  font-size: 65px;
}

.menu {
  background-color: darkslateblue;
  /* margin-top: 25px; */
  margin-left: 300px;
  margin-right: 300px;
  margin-bottom: 50px;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: whitesmoke;
  padding: 10px;
}

.room-image {
  border: 3px solid rgb(15, 71, 145);
  border-radius: 15px;
  width: 50%;
  margin: 40px;
}

.report {
  margin-left: 80px;
  /* text-align: center; */
}

.report > button {
  text-align: center;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 12px;
  padding-right: 12px;
  border: 2px solid black;
  background-color: black;
  border-radius: 30px;
  color: red;
}

.report > span {
  margin-left: 10px;
}

.last {
  padding-bottom: 18px;
}

#products {
  background-color: aliceblue;
  border: 5px solid rgb(74, 157, 196);
  border-radius: 20px;
  margin-top: 100px;
  margin-left: 300px;
  margin-right: 300px;
  padding-top: 20px;
  padding-bottom: 20px;
}
</style>
