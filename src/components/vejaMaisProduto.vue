<template>
    <div>
        <div class="vejaMaisContainer" v-bind:class="{ inativo: !vejaMais}">
      <div class="close" @click="fecharVejaMaisBtn"></div>
      <h2 class="header">
        {{produto.nome}}
      </h2>
      <p class="descricao">
        {{produto.descricao}}
      </p>
      <img src='https://placeimg.com/100/100'>
    </div>
    </div>
</template>

<script>
import {eventBus} from './../main'

export default {
    name: 'vejaMaisProduto',
    created: function() {
        eventBus.$on('vejaMaisProduto', (produtoAdicionado) => {
          eventBus.$emit('fecharVejaMaisCarrinho')
          this.mostraProduto(produtoAdicionado)
       })

        eventBus.$on('fecharVejaMaisProduto', () => {
         this.fecharVejaMaisBtn()
       })

    },
    data() {
        return {
            vejaMais: false,
            produto: {}
        }
    },
    methods: {
        fecharVejaMaisBtn() {
            this.vejaMais = false
        },
        mostraProduto(produto) {
            this.produto = produto
            this.vejaMais = true
        }
    }
}
</script>