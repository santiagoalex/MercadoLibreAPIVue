<template>
    <div id="busqueda">
        <form v-on:submit="formSubmit">
            <input type="text" v-model="list" placeholder="Buscar">
            <input type="submit" value="Buscar">
        </form>
    </div>
</template>

<script>
export default {
    name: 'busqueda',
    data(){
        return{
            list:''
        }
    },
    methods:{
        formSubmit(e){
            this.$emit('formSubmit', this.list);
            e.preventDefault();
            
        }
    } 
}
</script>

<style>

</style>
