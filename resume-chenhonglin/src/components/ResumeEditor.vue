<template>
  <div class="resumeEditor" ref="container" :class="{htmlMode:enableHtml}">
    <div v-if="enableHtml" v-html="result"></div>
    <div v-else>{{result}}</div>
  </div>
</template>

<script>
    import marked from 'marked'
    export default {
        name: "ResumeEditor",
        props:['markdown','enableHtml'],
        computed:{
          result:function(){
            return this.enableHtml ? marked(this.markdown) : this.markdown ;
          }
        },
        methods:{
          goBottom:function(){
            this.$refs.container.scrollTop=200000;
          },
          goTop:function(){
            this.$refs.container.scrollTop=0;
          }
        }
    }


</script>

<style scoped>
.htmlMode{
  animation:flip 2s;
}
  @keyframes flip {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
</style>
