<template>
        <div>
        <h1>
            escriba el articulo de que desea comprar
        </h1>
            <div class="list-group-item"><Item v-for="(obj, index) in object" :key="index" :title="obj.title" :price="obj.price"
            :seller="method(obj.seller.id)" :imgUrl="obj.thumbnail"></Item>
            </div>
        

    </div>
</template>

<script>
import Item from './Item.vue'
export default {
    name: 'lista',
    props: ['object', 'method', 'string'],
    components: {
    Item
  },
}

</script>

<style>
    .list-group-item {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
    }
</style>
