<template>
  <div id="app">
    <h1>Santiago Alexis Sanchez Zuleta - MercadoLibre</h1>
    <Busqueda v-on:formSubmit="list">    </Busqueda>
    <Lista :object='info' :method='nombrevendedor'/>
    
  </div>
</template>

<script>
import Busqueda from "./components/Busqueda.vue";
import Lista from "./components/Lista.vue";

export default {
  name: "app",
  components: {
    Busqueda,
    Lista,
  },
  data: function() {
    return {
      listademercado: "",
      usuarioid: "",
      producto: [],
      precio: [],
      vendedorid: [],
      nombrev: [],
      info: []
    };
  },
  
  methods: {
    
    list: async function(Busqueda) {
    //let Url = "https://api.mercadolibre.com/sites/MCO";
    let Url = "https://api.mercadolibre.com";
      this.$http
        .get(`${Url}/sites/MCO/search?q=${Busqueda}`)
        .then(res => {

            this.info= res.data.results
      
        });
    },
    nombrevendedor: function(identificacion){
      let Url = "https://api.mercadolibre.com";
      this.$http
      .get(`${Url}/users/${identificacion}`)
      .then(resp => {
        this.usuarioid=resp.body['nickname'];
        this.nombrev[0]=this.usuarioid;

      })
      return  this.nombrev[0].toString()
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
