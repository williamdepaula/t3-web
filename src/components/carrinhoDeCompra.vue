<template>
    <div class="carrinho" @click="vejaMaisCarrinhoBtn">
        <i class="material-icons">
        shopping_cart
        </i>
        <span class='badge badge-warning' id='lblCartCount'> {{quantidadeItensNoCarrinho}} </span>
        Carrinho
    </div>
</template>

<script>
import { eventBus } from '../main'

export default {
    name: "carrinhoDeCompra",
    created: function() {
        eventBus.$on('adicionarProdutoCarrinho', (produtoAdicionado) => {
         this.adicionarProdutoNoCarrinho(produtoAdicionado)
       })
    },
    data() {
        return {
            carrinho: []
        }
    },
    methods: {
        verificaSeExisteEAdiciona(produto) {
            let naoachou = true
            this.carrinho.forEach((item) => {
                if (item.id === produto.id) {
                    item.quantidade++
                    naoachou = false
                }
            })
            if (naoachou) {
                this.carrinho.push(produto)
            }
        },
        adicionarProdutoNoCarrinho({id}) {
            let item = {
                id: id,
                quantidade: 1
            }
            this.verificaSeExisteEAdiciona(item)
            eventBus.$emit('atualizarListaCarrinho', this.carrinho)
        },
        vejaMaisCarrinhoBtn() {
            eventBus.$emit('vejaMaisCarrinho', this.carrinho)
        }
    },
    computed: {
        quantidadeItensNoCarrinho() {
            let qtd = 0
            this.carrinho.forEach( item => {
                qtd = qtd + item.quantidade
            })     
            return qtd
        }
    }
}
</script>

<style lang="stylus" scoped>
.carrinho {
      color #fff
      text-align left  
      cursor pointer

      .badge {
        padding-left 9px
        padding-right 9px
        -webkit-border-radius 9px
        -moz-border-radius 9px
        border-radius 9px
      }

      .label-warning[href],
      .badge-warning[href] {
        background-color #c67605
      }
      #lblCartCount {
          font-size 12px
          background #ff0000
          color #fff
          padding 0 5px
          vertical-align top
          margin-left -10px
      }
    }
</style>