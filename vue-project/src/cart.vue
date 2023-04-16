<template>
<div>
    <p>{{ items }}</p>
    <p>{{ total }}</p>
</div>
</template>

<script>
export default {
   Name: "Cart",
   props: {
        items: Number,
        total: Number,
    },
}
</script>

<style scoped>

</style>

