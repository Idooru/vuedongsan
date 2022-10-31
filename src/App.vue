<template>
  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }} </a>
  </div>
  <h1 :style="element.myStyle">원룸샵</h1>
  <div id="products">
    <!-- <div v-for="(product, idx) in buried.products" :key="(product, idx)">
      <h3>{{ product }}</h3>
      <p>{{ buried.price[idx] }}</p>
    </div> -->
    <div>
      <h3>{{ buried.products[0] }}</h3>
      <p>50만원</p>
      <div class="report">
        <button>허위매몰신고</button>
        <span>신고수 : 0</span>
      </div>
    </div>
    <div>
      <h3>{{ buried.products[1] }}</h3>
      <p>60만원</p>
      <div class="report">
        <button>허위매몰신고</button>
        <span>신고수 : 0</span>
      </div>
    </div>
    <div>
      <h3>{{ buried.products[2] }}</h3>
      <p>70만원</p>
      <div class="report">
        <button>허위매몰신고</button>
        <span>신고수 : 0</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      menus: ["Home", "Product", "About"],
      buried: {
        products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
        price: [50, 60, 70],
      },
      element: { myStyle: "color: red" },
    };
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #1567b9;
}

/* h1 {
  text-decoration-style: dotted;
  font-size: 50px;
  font-weight: 900;
  color: #122436;
  text-shadow: 2px 2px 10px rebeccapurple;
} */

.menu {
  background-color: darkslateblue;
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
