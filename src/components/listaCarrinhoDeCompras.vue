<template>
    <div class="vejaMaisCarrinho" v-bind:class="{ inativo: !vejaMaisCarrinho}">
      <div class="close" @click="fecharVejaMaisCarrinhoBtn"></div>
      <div class="lista-carrinho">

         <div class="produto-carrinho" v-for="produto in carrinhoDeCompras" :key="produto.id">
          <div class="imagem">
            <img src='https://placeimg.com/100/50'>
          </div>
          <div class="infos">
            <h3 class="header">
              {{produto.nome}}
            </h3>
            <p class="preco">
              R$ {{produto.preco}}
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>{{produto.quatidade_estoque}}</span>
            </p>
          </div>
          <div class="remover">
            <i class="material-icons">
              delete
            </i>
          </div>
        </div>

      </div> <!-- /lista-carrinho -->
      <div class="total-carrinho">
        <h3>Total</h3>
        <p>
          R$ 2599,99
        </p>
        <div class="botao">Comprar</div>
      </div> <!-- /total-carrinho -->
      
    </div>
</template>
<script>
import { eventBus } from '../main'

export default {
    name: 'listaCarrinhoDeCompras',
    created: function() {
        eventBus.$on('vejaMaisCarrinho', (carrinho) => {
            eventBus.$emit('fecharVejaMaisProduto')
            this.buscarProdutosEAbrir(carrinho)
        })

        eventBus.$on('fecharVejaMaisCarrinho', () => {
            this.fecharVejaMaisCarrinhoBtn()
        })

        eventBus.$on('atualizarListaCarrinho', (carrinho) => {
            this.atualizarCarrinho(carrinho)
        })
    },
    data() {
        return {
            vejaMaisCarrinho: false,
            produtos: [],
            carrinhoDeCompras: [],
            carrinho: []
        }
    },
    methods: {
        fecharVejaMaisCarrinhoBtn() {
            this.vejaMaisCarrinho = false
        },
        buscarProdutosEAbrir(carrinho) {
            this.atualizarCarrinho(carrinho)
            this.vejaMaisCarrinho = true
        },
        atualizarCarrinho(carrinho) {
            this.carrinho = carrinho
            this.buscaProdutosCarrinho()
        },
        buscaProdutosCarrinho() {
            this.produtos = []
            const getProdutoUrl = id => `http://my-json-server.typicode.com/williamdepaula/t3-web/produtos/${id}`

            const produtoPromises = []

            this.carrinho.forEach( item => {
                produtoPromises.push(fetch(getProdutoUrl(item.id)).then(response => response.json()))
            })

            Promise.all(produtoPromises)
                .then(produtos => {
                    console.log("Produto: ", produtos)
                    this.produtos = produtos
                    this.organizaCarrinho()
                })
            
        },
        buscaQuatidadeDesejada(idItem) {
            console.log("idItem:", idItem)
            this.carrinho.forEach( item => {
                if (idItem === item.id) {
                    console.log("Item", item)
                    return item.quantidade
                }
            })
            return 0
        },
        organizaCarrinho() {
            console.log("Organiza: ", this.produtos)
            this.carrinhoDeCompras = []
            this.produtos.forEach( item => {
                let qtd = this.buscaQuatidadeDesejada(item.id)
                console.log("Qtd: ", qtd)
                let prod = {
                    id: item.id,
                    descricao: item.descricao,
                    nome: item.nome,
                    preco: item.preco,
                    quantidade: qtd
                }
                this.carrinhoDeCompras.push(prod)
            })
        }
    }
}
</script>