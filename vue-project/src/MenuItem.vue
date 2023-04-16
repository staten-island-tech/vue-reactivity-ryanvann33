<template>
  <div class="cards">
    <div class="box">
      <img :src="img" alt="" />
      <h1 class="name">{{ name }}</h1>
      <p class="price">${{ price }}</p>
      <button @click="$emit('buttonClicked')">Add to Cart</button>
    </div>
  </div>
</template>

<script>
export default {
  Name: 'Fruit',
  props: {
    img: String,
    name: String,
    price: Number
  }
}
</script>

<style scoped>
.cards {
  width: 100%;
  height: 100%;
  display: flex;
  flex-wrap: wrap;
}

.box {
  height: 30%;
  width: 60%;
  margin: 30px;
  background-color: rgb(119,136,153);
  border-radius: 20px;
  border-width: 3px;
  border-style: solid;
  border-color: rgb(0, 0, 0);
}

img {
  margin: 0 auto;
  display: block;
  height: 100px;
}

.name {
  font-size: 30px;
  text-align: center;
}

.price {
  font-size: 18px;
  text-align: center;
}

.button {
  align-content: center;
}
</style>
