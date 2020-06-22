<template>
    <div>
      <produto v-for="produto in produtos" :key="produto.id" :produto="produto"/>      
    </div>
</template>

<script>
import produto from './produto'

export default {
    name: 'listaProdutos',
    components: {
      produto
    },

    data() {
        return {
            produtos: []
        }
    },
    created: function() {
       this.buscaProdutos()
    },
    methods: {
        buscaProdutos() {
          fetch('http://my-json-server.typicode.com/williamdepaula/t3-web/produtos')
          .then( response => response.json())
          .then( json => this.produtos = json)
        }        
    }
}
</script>
