<template>
  <div id="app">

    <div class="container">
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
      <div class="close"></div>
      <h2 class="header">
        Nome do produto
      </h2>
      <p class="descricao">
        Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus. Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.Nullam posuere turpis vel lacinia luctus.
      </p>
      <img src='https://placeimg.com/100/100'>
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
      vejaMais: false
    }
  },
  methods: {
    vejaMaisBtn() {
      this.vejaMais = !this.vejaMais
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
  }

  .container {
    padding 20px
    text-align center

    .produto {
      position relative
      overflow: hidden;
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
  
</style>
