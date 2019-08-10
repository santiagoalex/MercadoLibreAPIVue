<template>
    <div class="card centralizar" style="width: 20rem;">
        <img class="card-img-top" :src="imgUrl" alt="Card image cap">
        <div class="card-body">
            <h1 class="card-title">{{title}}</h1>
            <p class="card-text">Su vendedor : {{seller}}</p>
            <p class="card-text">Su precio : ${{price}}</p>
        </div>
    </div>
</template>
<script>
export default {
  name: "Item",
  props: {
    title: String,
    price: Number,
    seller: Number,
    imgUrl: String
  }
};
</script>

<style>
    .centralizar{
        display: block;
    margin-left: auto;
    margin-right: auto
    }
</style>