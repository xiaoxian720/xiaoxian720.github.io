<template>
    <div class="styleEditor" ref="container">
      <div class="code" v-html="codeInStyle"></div>
      <pre v-html="highlightedCode"></pre>
    </div>
</template>

<script>
    import Prism from 'prismjs'

    export default {
        name: "StyleEditor",
        props:['code'],
        computed:{
          highlightedCode:function(){
            return Prism.highlight(this.code,Prism.languages.css)
          },
          codeInStyle:function(){
            return `<style>${this.code}</style>`
          }
        },
        mounted:function(){
          console.log(this.code);
        },
        methods:{
          goBottom(){
            this.$refs.container.scrollTop = 100000;
          }
        }
    }
</script>

<style scoped>
  .code{
    display:none;
  }
</style>
