<template>
  <div class="card">
    <h2>{{ name }}</h2>
    <h3>Price: ${{ price }}</h3>
    <img :src="image" :alt="name" /><br />

    <div class="details">
      <h4 id="details">Details:</h4>
      <p>Processor: {{ processor }}</p>
      <p>Ram: {{ memory }}</p>
      <p>Hard Drive: {{ harddrive }}</p>
      <p>Color: {{ color }}</p>
    </div>
    <button @click="removeFromCart" class="button" type="click">
      Remove from Cart
    </button>
  </div>
</template>

<script>
import { cartList } from "../cartList";
import { Price } from "../totalPrice";
export default {
  name: "Card",
  props: {
    name: String,
    price: Number,
    image: String,
    processor: String,
    memory: String,
    harddrive: String,
    color: String,
    totalPrice: Number,
  },
  methods: {
    removeFromCart: function (index) {
      cartList.splice(index, 1);
      let newPrice = (Price.totalPrice -= this.price);
      //console.log(cartList);
      //console.log(newPrice);
    },
  },
};
</script>

<style scoped>
.card {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  justify-content: flex-start;
  width: 20%;
  height: auto;
  margin: 1.45rem;
  padding: 0.5rem;
  border: 2px #3a3a93 solid;
  text-align: center;
  align-items: center;
  background-color: #3a3a93;
}

img {
  object-fit: cover;
  border-radius: inherit;
  height: 10rem;
  width: auto;
}

#details {
  text-decoration: underline;
}

.button {
  margin-top: 1rem;
  appearance: none;
  background-color: #fafbfc;
  border: 1px solid rgba(27, 31, 35, 0.15);
  border-radius: 6px;
  box-shadow: rgba(27, 31, 35, 0.04) 0 1px 0,
    rgba(255, 255, 255, 0.25) 0 1px 0 inset;
  box-sizing: border-box;
  color: #24292e;
  cursor: pointer;
  display: inline-block;
  font-family: -apple-system, system-ui, "Segoe UI", Helvetica, Arial,
    sans-serif, "Apple Color Emoji", "Segoe UI Emoji";
  font-size: 14px;
  font-weight: 500;
  line-height: 20px;
  list-style: none;
  padding: 6px 16px;
  position: relative;
  transition: background-color 0.2s cubic-bezier(0.3, 0, 0.5, 1);
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  vertical-align: middle;
  white-space: nowrap;
  word-wrap: break-word;
}

.button:hover {
  background-color: #f3f4f6;
  text-decoration: none;
  transition-duration: 0.1s;
}

.button:disabled {
  background-color: #fafbfc;
  border-color: rgba(27, 31, 35, 0.15);
  color: #959da5;
  cursor: default;
}

.button:active {
  background-color: #edeff2;
  box-shadow: rgba(225, 228, 232, 0.2) 0 1px 0 inset;
  transition: none 0s;
}

.button:focus {
  outline: 1px transparent;
}

.button:before {
  display: none;
}

.button-4:-webkit-details-marker {
  display: none;
}
</style>
