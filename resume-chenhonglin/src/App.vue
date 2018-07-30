<template>
  <div id="app">
    <StyleEditor :code="currentStyle" ref="styleEditor"></StyleEditor>
    <ResumeEditor :markdown="currentMarkdown" ref="resumeEditor" :enableHtml="enableHtml"></ResumeEditor>
  </div>
</template>

<script>
  import StyleEditor from './components/StyleEditor'
  import ResumeEditor from './components/ResumeEditor'
  import './assets/init.css'

  export default {
    name:'app',
    components:{
      StyleEditor,
      ResumeEditor
    },
    data:function(){
      return {
        interval:50,
        enableHtml:true,
        currentStyle:'',
        fullStyle:[
          `/*
*您好，我是陈虹林，女，27岁，WEB前端开发工程师一枚，目前正在找工作
*如果您是HR，感谢您花时间来阅览我的简历
*如果您是技术爱好者，喜欢这个效果，可以到我的GitHub下载源码
*好了，以下是我的简历，o(*￣︶￣*)o
*/

/*首先所有元素加上过渡效果*/
* {
  transiton: all .3s;
}
/*白色背景有点刺眼了，给点颜色吧*/
body {
  color: rgb(122,122,122);
  background:rgb(4,61,75);
}
/*好像文字离边框有点近了，调整下*/
.styleEditor {
  padding: .5em;
  border: 1px solid;
  margin: .5em;
  overflow: auto;
  width: 45vw;
  height: 90vh;
}
/*既然有代码，就高亮显示下吧*/
.token.selector {
  color: rgb(133,153,0);
}
.token.property {
  color: rgb(187,137,0);
}
.token.punctuation {
  color: yellow;
}
.token.function {
  color: rgb(42,161,152);
}
/*看起来好点了，再加点3D效果吧*/
html {
  perspective: 1000px;
}
.styleEditor {
  position: fixed;
  left: 0;
  top: 0;
  -webkit-transition: none;
          transition: none;
  -webkit-transform: rotateY(10deg) translateZ(-100px);
          transform: rotateY(10deg) translateZ(-100px);
}

/*接下来准备一个编辑器*/
.resumeEditor {
  background: rgb(255,255,255);
  position: fixed;
  right: 0;
  top: 0;
  padding: .5em;
  margin: .5em;
  width: 48vw;
  max-height: 95vh;
  border: 1px solid;
  color: rgb(55,55,55);
  overflow: auto;
}
/*OK,准备工作就绪，现在开始写简历*/
`,
`/*
*额...
*这个简历是MarkDown格式的，需要变成对HR更友好的格式
*这个简单，用开源工具翻译成HTML就行了
*/
`,
`/*再对HTML加点样式*/
.resumeEditor {
  padding: 2em;
  color:  rgba(0,0,0);
}
.resumeEditor h3,.resumeEditor h4 {
  display: inline-block;
  margin: .5em 0 .5em;
}
.resumeEditor blockquote {
  margin: 1em;
  padding: .5em;
  background: #ddd;
}
`

],
        currentMarkdown:'',
        fullMarkdown:`
<img src="static/01.png" width="105" height="140" align="left" />

### 陈虹林[求职目标：WEB前端工程师]
___

### 基本信息
___

|·|姓名:|陈虹林|·|毕业院校:|暨南大学|
|:----:|:----|:----|:----:|:----|:----|
|·|出生年月:|1990-07|·|学历:|本科|
|·|联系电话:|17623239319|·|专业:|旅游管理|
|·|邮箱:|929474823@qq.com|·|现居地:|重庆市渝北区|
___

### 前端技能
___

- 熟练运用HTML5、CSS3、JavaScript、Ajax、DOM、JQuery等核心前端技术实现页面交互
- 熟练运用PHP、Node.js进行MySQL、MongoDB数据库CRUD操作
- 熟悉Bootstrap、Vue、Angular、React等前端框架
- 熟悉前端开发常用工具npm、webpack、gulp等，熟练运用PS进行图片处理工作
___

### 工作经历
___

#### 2016.03-2017.09             重庆市锦正园林绿化有限公司               市场部  主管
+ 主要负责项目管理、客户关系维护、投标文件撰写及现场答标、公司流程梳理及优化、内部培训（管理培训及商务培训）等
+ 利用微信企业号、钉钉等免费系统实现线上公司人员管理、合同及账款管理、费用报销管理及CRM管理

#### 2015.01-2016.01             河北东云网络科技有限公司                 运营部  主管
+ 主要负责微信公众号代运营、微信平台二次开发、软件开发、活动策划与执行
+ 开发部分事项：与客户对接沟通开发需求、撰写需求文档报客户审批；与外包方沟通项目周期、人员安排；组织客户与外包方进行技术周期进展汇报；跟进项目上线及后期维护

#### 2011.11-2014.11             福建星网锐捷网络有限公司                 商务部  商务专员
+ 先后服务深圳、北京办事处、商务部总部，主要进行商务支持（订单、合同、账款管理、销售利润核算）工作
+ 熟练使用OA系统、CRM系统、DRP系统、OEM系统，并对部门人员进行系统操作培训，与IT部门对接商务部日常开发需求，公司数据库切换后数据核对工作
___

### 项目经验
___
+ 一点绿线上绿植销售平台（H5、CSS3、JS、JQuery、MySQL、PHP等）：仿淘宝商城的绿植网上销售平台，主页展示、分类浏览、条件检索、商品详情页、购物车页面、支付页面、登录注册页面、个人中心页面
+ 锦正园林官网（Bootstrap、MySQL、PHP、JQuery等）：实现公司主页、主营业务、合作伙伴、公司新闻、联系页面的跨平台展示
+ 个人博客（Node.js、MongoDB）：前台注册、登录、内容展示、评论展示等，后台用户管理、内容管理等
+ H5游戏（JavaScript、Canvas）：flappy bird、贪吃蛇、扫雷等
___

### 获奖情况
___
+ 2013年福建星网锐捷网络科技有限公司“最佳助理奖”（公司级TOP3）
+ 2014年福建星网锐捷网络科技有限公司商务部“最佳新人奖”“主人翁精神奖”（部门级TOP5）
+ 2015年河北东云网络科技有限公司“先进个人奖”（公司级）
+ 2017年重庆市锦正园林绿化有限公司“优秀团队奖”（公司级）
___

### 技能证书
___
**大学英语四/六级（CET-4/6）**
**会计从业资格证书（会计电算化证书）**
**初级园林工程师证书**
**驾驶证C1**
`
      }
    },
    created:function(){
      this.makeResume();
    },
    methods:{
      makeResume: async function () {
        await this.progressivelyShowStyle(0)
        await this.progressivelyShowResume()
        await this.progressivelyShowStyle(1)
        await this.showHtml()
        await this.progressivelyShowStyle(2)
        await this.$refs.resumeEditor.goTop();
      },
      showHtml: function () {
        return new Promise((resolve, reject) => {
          this.enableHtml = true
          resolve()
        })
      },
      /*逐步显示样式*/
      progressivelyShowStyle(n){
        return new Promise((resolve, reject) => {
          let interval = this.interval
          let showStyle = (async function () {
            let style = this.fullStyle[n]
            if (!style) { return }
            // 计算前 n 个 style 的字符总数
            let length = this.fullStyle.filter((_, index) => index <= n).map((item) => item.length).reduce((p, c) => p + c, 0)
            let prefixLength = length - style.length
            if (this.currentStyle.length < length) {
              let l = this.currentStyle.length - prefixLength
              let char = style.substring(l, l + 1) || ' '
              this.currentStyle += char
              if (style.substring(l - 1, l) === '\n' && this.$refs.styleEditor) {
                this.$nextTick(() => {
                  this.$refs.styleEditor.goBottom()
                })
              }
              setTimeout(showStyle, interval)
            } else {
              resolve()
            }
          }).bind(this)
          showStyle()
        })
      },
      progressivelyShowResume() {
        return new Promise((resolve, reject) => {
          let length = this.fullMarkdown.length
          let interval = this.interval
          let showResume = () => {
            if (this.currentMarkdown.length < length) {
              this.currentMarkdown = this.fullMarkdown.substring(0, this.currentMarkdown.length + 1)
              let lastChar = this.currentMarkdown[this.currentMarkdown.length - 1]
              let prevChar = this.currentMarkdown[this.currentMarkdown.length - 2]
              if (prevChar === '\n' && this.$refs.resumeEditor) {
                this.$nextTick(() => this.$refs.resumeEditor.goBottom())
              }
              setTimeout(showResume, interval)
            } else {
              resolve()
            }
          }
          showResume()
        })
      }
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
  html{
    min-height:100vh;
  }
</style>
