<template>
  <div id="app">

    <div class="container">
      <div class="carrinho" @click="vejaMaisCarrinhoBtn">
        <i class="material-icons">
          shopping_cart
        </i>
        <span class='badge badge-warning' id='lblCartCount'> 5 </span>
        Carrinho
      </div>
      <div class="produto">
        <img src='https://placeimg.com/200/100'>
        <h2 class="header">
          Nome do produto
        </h2>
        <p class="descricao">
          Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.
        </p>
        <p class="preco">
          R$ 230,99
        </p>
        <div class="botao">add carrinho</div>
        <div class="vejamais" @click="vejaMaisBtn()">Saiba mais</div>
      </div>

      <div class="produto">
        <img src='https://placeimg.com/200/100'>
        <h2 class="header">
          Nome do produto
        </h2>
        <p class="descricao">
          Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.
        </p>
        <p class="preco">
          R$ 230,99
        </p>
        <div class="botao">add carrinho</div>
        <div class="vejamais">Saiba mais</div>
      </div>

      <div class="produto">
        <img src='https://placeimg.com/200/100'>
        <h2 class="header">
          Nome do produto
        </h2>
        <p class="descricao">
          Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.
        </p>
        <p class="preco">
          R$ 230,99
        </p>
        <div class="botao">add carrinho</div>
        <div class="vejamais">Saiba mais</div>
      </div>

      <div class="produto">
        <img src='https://placeimg.com/200/100'>
        <h2 class="header">
          Nome do produto
        </h2>
        <p class="descricao">
          Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.
        </p>
        <p class="preco">
          R$ 230,99
        </p>
        <div class="botao">add carrinho</div>
        <div class="vejamais">Saiba mais</div>
      </div>

      <div class="produto">
        <img src='https://placeimg.com/200/100'>
        <h2 class="header">
          Nome do produto
        </h2>
        <p class="descricao">
          Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.
        </p>
        <p class="preco">
          R$ 230,99
        </p>
        <div class="botao">add carrinho</div>
        <div class="vejamais">Saiba mais</div>
      </div>
      
    </div>

    <div class="vejaMaisContainer" v-bind:class="{ inativo: !vejaMais}">
      <div class="close" @click="fecharVejaMaisBtn"></div>
      <h2 class="header">
        Nome do produto
      </h2>
      <p class="descricao">
        Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.
      </p>
      <img src='https://placeimg.com/100/100'>
    </div>

    <div class="vejaMaisCarrinho" v-bind:class="{ inativo: !vejaMaisCarrinho}">
      <div class="close" @click="fecharVejaMaisCarrinhoBtn"></div>
      <div class="lista-carrinho">

         <div class="produto-carrinho">
          <div class="imagem">
            <img src='https://placeimg.com/100/50'>
          </div>
          <div class="infos">
            <h3 class="header">
              Nome do produto
            </h3>
            <p class="preco">
              R$ 230,99
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>2</span>
            </p>
          </div>
          <div class="remover">
            <i class="material-icons">
              delete
            </i>
          </div>
        </div>

        <div class="produto-carrinho">
          <div class="imagem">
            <img src='https://placeimg.com/100/50'>
          </div>
          <div class="infos">
            <h3 class="header">
              Nome do produto
            </h3>
            <p class="preco">
              R$ 230,99
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>2</span>
            </p>
          </div>
          <div class="remover">
            <i class="material-icons">
              delete
            </i>
          </div>
        </div>

        <div class="produto-carrinho">
          <div class="imagem">
            <img src='https://placeimg.com/100/50'>
          </div>
          <div class="infos">
            <h3 class="header">
              Nome do produto
            </h3>
            <p class="preco">
              R$ 230,99
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>2</span>
            </p>
          </div>
          <div class="remover">
            <i class="material-icons">
              delete
            </i>
          </div>
        </div>

        <div class="produto-carrinho">
          <div class="imagem">
            <img src='https://placeimg.com/100/50'>
          </div>
          <div class="infos">
            <h3 class="header">
              Nome do produto
            </h3>
            <p class="preco">
              R$ 230,99
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>2</span>
            </p>
          </div>
          <div class="remover">
            <i class="material-icons">
              delete
            </i>
          </div>
        </div>

        <div class="produto-carrinho">
          <div class="imagem">
            <img src='https://placeimg.com/100/50'>
          </div>
          <div class="infos">
            <h3 class="header">
              Nome do produto
            </h3>
            <p class="preco">
              R$ 230,99
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>2</span>
            </p>
          </div>
          <div class="remover">
            <i class="material-icons">
              delete
            </i>
          </div>
        </div>

        <div class="produto-carrinho">
          <div class="imagem">
            <img src='https://placeimg.com/100/50'>
          </div>
          <div class="infos">
            <h3 class="header">
              Nome do produto
            </h3>
            <p class="preco">
              R$ 230,99
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>2</span>
            </p>
          </div>
          <div class="remover">
            <i class="material-icons">
              delete
            </i>
          </div>
        </div>

        <div class="produto-carrinho">
          <div class="imagem">
            <img src='https://placeimg.com/100/50'>
          </div>
          <div class="infos">
            <h3 class="header">
              Nome do produto
            </h3>
            <p class="preco">
              R$ 230,99
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>2</span>
            </p>
          </div>
          <div class="remover">
            <i class="material-icons">
              delete
            </i>
          </div>
        </div>

        <div class="produto-carrinho">
          <div class="imagem">
            <img src='https://placeimg.com/100/50'>
          </div>
          <div class="infos">
            <h3 class="header">
              Nome do produto
            </h3>
            <p class="preco">
              R$ 230,99
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>2</span>
            </p>
          </div>
          <div class="remover">
            <i class="material-icons">
              delete
            </i>
          </div>
        </div>

        <div class="produto-carrinho">
          <div class="imagem">
            <img src='https://placeimg.com/100/50'>
          </div>
          <div class="infos">
            <h3 class="header">
              Nome do produto
            </h3>
            <p class="preco">
              R$ 230,99
            </p>
            <p class="quantidade">
              Quantidade: 
              <span>2</span>
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
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      vejaMais: false,
      vejaMaisCarrinho: false
    }
  },
  methods: {
    vejaMaisBtn() {
      this.vejaMais = !this.vejaMais
    },
    fecharVejaMaisBtn() {
      this.vejaMais = false
    },
     vejaMaisCarrinhoBtn() {
      this.vejaMaisCarrinho = !this.vejaMaisCarrinho
    },
    fecharVejaMaisCarrinhoBtn() {
      this.vejaMaisCarrinho = false
    }
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

    .produto {
      position relative
      overflow hidden
      display inline-block
      width 200px
      height 260px
      border-radius 4px
      background-color rgba(255,255,255,.45)
      margin 20px

      img {
        min-height 100px
        position relative
        border-top-right-radius 4px
        border-top-left-radius 4px
        clip-path polygon(0 100%, 0 0, 100% 0, 100% 70%)
        transition all .2s ease

        &:hover {
          clip-path polygon(0 100%, 0 0, 100% 0, 100% 100%)
          transform scale(1.1)
        }
      }

      h2 {
        text-align left 
        color #fff
        font-size 14px
        font-font-weight bold
        margin-bottom 4px
        margin-left 15px
      }

      .descricao {
        text-align left 
        font-size 11px
        color #fff
        max-height 30px
        overflow hidden
        margin-left 15px
        margin-right 15px
        text-align justify
      }

      .preco {
        text-align right 
        font-size 18px
        color #fff
        margin-top 6px
        margin-bottom 6px
        margin-right 15px
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
          content: "add_circle_outline";
          color #00fefe
          margin-left 30px
          position absolute
          transition all .2s ease
        }
      }

      .vejamais {
        position absolute
        bottom 20px
        font-size 11px
        color #fff
        cursor pointer
        margin-left 15px

        &:before {
          font-family: "Material Icons";
          content: "help_outline";
          margin-right 3px
          font-size 13px
        }
      }
    }
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
