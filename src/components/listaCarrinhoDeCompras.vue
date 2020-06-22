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
              R$ {{formataPreco(produto.preco)}}
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>{{produto.quantidade}}</span>
            </p>
          </div>
          <div class="remover" @click="removerItemCarrinho(produto.id)" >
            <i class="material-icons">
              delete
            </i>
          </div>
        </div>

      </div> <!-- /lista-carrinho -->
      <div class="total-carrinho">
        <h3>Total</h3>
        <p>
          R$ {{totalCarrinho}}
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
    computed: {
      totalCarrinho() {
        let total = 0.0
        this.carrinhoDeCompras.forEach( item => {
          total += item.preco * item.quantidade
        })
        return parseFloat(total).toFixed(2).replace('.', ',')
      }
    },
    methods: {
        removerItemCarrinho(id) {
          this.carrinho.forEach( (item, index) => {
            if (item.id === id) {
              this.carrinho.splice(index, 1)
            }
          })

          this.buscaProdutosCarrinho()
        },
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
                    this.produtos = produtos
                    this.organizaCarrinho()
                })     
        },
        buscaQuatidadeDesejada(idItem) {
            let qtd = 0
            this.carrinho.forEach( item => {
                if (idItem === item.id) {
                    qtd = item.quantidade
                }
            })
            return qtd
        },
        organizaCarrinho() {
            this.carrinhoDeCompras = []
            this.produtos.forEach( item => {
                let prod = {
                    id: item.id,
                    descricao: item.descricao,
                    nome: item.nome,
                    preco: item.preco,
                    quantidade: this.buscaQuatidadeDesejada(item.id)
                }
                this.carrinhoDeCompras.push(prod)
            })
        },
        formataPreco(preco) {
        return parseFloat(preco).toFixed(2).replace('.', ',')
      }
    }
}
</script>