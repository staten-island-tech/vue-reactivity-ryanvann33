<template>
  <div>
    <div class="topbar">
      <p class="text">Cart</p>
      <Cart class="cart" :items="items" :total="total" />
    </div>
    <h1 class="ck">Ryan's Menu</h1>
    <div class="box">
      <Fruit
        v-for="(menu, index) in menus"
        :key="index"
        :img="menu.img"
        :name="menu.name"
        :price="menu.price"
        @button-clicked="addToCart(menu)"
      />
    </div>
  </div>
</template>

<script>
import Fruit from "./MenuItem.vue";
import Cart from "./cart.vue";

export default {
  components: {
    Fruit,
    Cart,
  },
  data() {
    return {
      items: 0,
      total: 0,
      menus: [
        {
          img: "https://natashaskitchen.com/wp-content/uploads/2020/03/Pan-Seared-Steak-4.jpg",
          name: "Steak",
          price: 1,
        },
        {
          img: "https://food.fnr.sndimg.com/content/dam/images/food/fullset/2011/6/3/1/FNM_070111-Fried-Chicken-026_s4x3.jpg.rend.hgtvcom.826.620.suffix/1382539796174.jpeg",
          name: "Chicken",
          price: 2,
        },
        {
          img: "https://thewoksoflife.com/wp-content/uploads/2022/06/spicy-thai-basil-clams-9-650x872.jpg",
          name: "Clams",
          price: 89,
        },
        {
          img: "https://www.whiskaffair.com/wp-content/uploads/2020/07/Hibachi-Fried-Rice-2-1.jpg",
          name: "Fried Rice",
          price: 4,
        },
      ],
    };
  },
  methods: {
    addToCart(menu) {
      this.items = this.items + 1;
      this.total = this.total + menu.price;
    },
  },
};
</script>

<style scoped>
.topbar {
  height: 100px;
  width: 100%;
  position: absolute;
  display: flex;
  top: 0px;
  left: 0px;
  background-color: rgb(205, 92, 92);
  justify-content: right;
}

.ck {
  color: white;
  margin: auto;
  position: relative;
  display: block;
  margin-top: 25px;
  text-align: center;
  font-size: 50px;
}

.cart {
  margin-top: 450px;
  margin-right: 1800px;
  position: relative;
  font-size: 20px;
}
.text {
  margin-top: 430px;
  font-size: 30px;
}
.box {
  display: flex;
  flex-direction: row;
}
</style>
