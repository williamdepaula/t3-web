<template>
    <div>
      <div v-for="produto in produtos" :key="produto.id" class="produto">
        <img :src="produto.url_imagem">
        <h2 class="header">
          {{produto.nome}}
        </h2>
        <p class="descricao">
          {{produto.descricao}}
        </p>
        <p class="preco">
          R$ {{produto.preco}}
        </p>
        <div class="botao">add carrinho</div>
        <div class="vejamais" @click="vejaMaisBtn()">Saiba mais</div>
      </div>

      
    </div>
</template>

<script>

export default {
    name: 'listaProdutos',
    components: {
    },

    data() {
        return {
            produtos: []
        }
    },
    created: function() {
       //this.buscaProdutos()
    },
    methods: {
        buscaProdutos() {
          fetch('http://my-json-server.typicode.com/williamdepaula/test-kanttum/processos')
          .then( response => response.json())
          .then( json => this.produtos = json)
        }
    }
}
</script>

<style lang="stylus" scoped>
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
</style>