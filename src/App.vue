<template>
  <div id="app">

    <div class="container">
     <carrinho-de-compra/>
     <lista-produtos></lista-produtos>
    </div>

    <veja-mais-produto/>
    
    <lista-carrinho-de-compras />
    
  </div>
</template>

<script>

import listaProdutos from './components/listaProdutos.vue'
import carrinhoDeCompra from './components/carrinhoDeCompra.vue'
import vejaMaisProduto from './components/vejaMaisProduto.vue'
import listaCarrinhoDeCompras from './components/listaCarrinhoDeCompras.vue'

export default {
  name: 'App',
  components: {
    listaProdutos,
    carrinhoDeCompra,
    vejaMaisProduto,
    listaCarrinhoDeCompras
  }
}
</script>

<style lang="stylus">

  @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

  * {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    box-sizing: border-box;
  }

  body {
    background-color: #0b0b0b;
    font-family: 'Roboto', sans-serif;
    min-width 540px

  }

  .container {
    padding 20px
    text-align center    
  }

  .vejaMaisContainer {
    position fixed
    height 100vh
    width 400px
    background-color rgba(0,0,0,.90)
    top 0
    right 0
    color #fff
    padding 30px
    transition all .3s ease

    .close {
      display inline-table
      height 20px
      width 20px
      float right 
      cursor pointer
      -webkit-transition: -webkit-transform .8s ease-in-out;
      transition:         transform .8s ease-in-out;

      &:before {
        font-family: "Material Icons";
        content "close"
        font-size 20px
      }

      &:hover {
        -webkit-transform: rotate(360deg);
        transform: rotate(360deg);
      }
    }

    .header {
      margin-bottom 30px
      font-size 18px
    }

    .descricao {
      font-size 12px
      margin-bottom 20px
    }

    img {
      display inline-block
      border-radius 4px
      margin 5px
    }

    &.inativo {
      right -100%
    }

  }

  .vejaMaisCarrinho {
    position fixed
    height 100vh
    width 400px
    background-color rgba(0,0,0,.90)
    top 0
    right 0
    color #fff
    padding 30px
    transition all .3s ease

    .close {
      display inline-table
      height 20px
      width 20px
      float right 
      cursor pointer
      -webkit-transition: -webkit-transform .8s ease-in-out;
      transition:         transform .8s ease-in-out;

      &:before {
        font-family: "Material Icons";
        content "close"
        font-size 20px
      }

      &:hover {
        -webkit-transform: rotate(360deg);
        transform: rotate(360deg);
      }
    }

    &.inativo {
      right -100%
      display none
    }

    .lista-carrinho {
      margin-top 15px
      overflow-y auto
      height inherit
      display inline flow-root list-item
    }

    .produto-carrinho {
      margin-top 20px
      display inline-flex
      width 100%

      .imagem {
        width auto
        margin-top auto
        margin-bottom auto
      }

      .infos {
        width 50%
        margin auto 0 auto 10px

        .header {
          margin 3px
          font-size 17px
        }

        .preco {
          margin 3px
          width max-content
          float inline-start
          font-size 14px
        }

        .quantidade {
          margin 3px
          width max-content
          float inline-start
          font-size 10px
          margin-left 5px
        }
      }

      .remover {
        width: 20%;
        text-align: end;
        margin-top: auto;
        margin-bottom: auto;
        display none
      }
    }

    .produto-carrinho:hover {
      .remover {
        display inline
        cursor pointer
      }
    }

    .total-carrinho {
      position absolute
      bottom 0px
      background-color black
      width -moz-available
      right 46px
      padding-left 33px

      h3 {
        width max-content
        float inline-start
        margin-right 5px
      }

      p {
        font-size 20px
        display flex
      }

      .botao {
        font-size 11px
        font-font-weight bold
        float right 
        border 2px solid #00fefe
        border-radius 20px
        padding 10px
        color #00fefe
        bottom 10px
        right 10px
        overflow hidden
        position absolute
        cursor pointer
        transition all .2s ease

        &:hover {
          padding-right 25px

          &:after {
            margin-left 5px
          }
        }

        &:after {
          font-family: "Material Icons";
          content: "payment";
          color #00fefe
          margin-left 30px
          position absolute
          transition all .2s ease
        }
      }
    }

  }
  
</style>
