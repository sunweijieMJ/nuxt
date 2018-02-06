<template>
  <div class="header">
    <h1 @click="goHome">
      <img src="../../assets/icon/nav_ic_logo.png" alt="">
    </h1>
    <nav>
      <a href="javascript:;" v-for="(item,index) in tab" :key="index" @click="chooseTab(item.router)" :class="{active:activeTab===item.router}">{{item.title}}</a>
    </nav>
  </div>
</template>
<script>
export default {
  data(){
    return {
      tab: [
        {
          title: '首页',
          router: 'Home',
        },
        {
          title: '关于我们',
          router: 'AboutUs',
        },
        {
          title: '瓴里产品',
          router: 'LaneHubProduct',
        },
        {
          title: '商业合作',
          router: 'Partners',
        },
        {
          title: '瓴里 App',
          router: 'LaneHubApp',
        }
      ],
      activeTab: {}
    }
  },
  created(){
    this.chooseTab(this.$route.name);
  },
  methods: {
    chooseTab(name){
      if(name === 'LaneHubApp'){
        this.download();
        return;
      }
      this.activeTab = name;
      this.$router.push({name:name});
    },
    goHome(){
      this.$router.push({name:'Home'});
    },
    download(){
      let height = document.documentElement.offsetHeight;
      this.setScrollTop(height);
    },
    setScrollTop(scroll_top){
      window.pageYOffset = scroll_top;
      document.documentElement.scrollTop = scroll_top;
      document.body.scrollTop = scroll_top;
    }
  }
}
</script>
<style lang="less" scoped>
@import '../../assets/style/tool.less';
  .header{
    width: 100%;
    min-width: 1280px;
    position: absolute;
    h1{
      margin: 34px 40px;
      float: left;
      cursor: pointer;
      img{
        width: 154px;
        display: block;
      }
    }
    nav{
      float: right;
      margin: 33px 40px 0 0;
      position: relative;
      a{
        font-size: 16px;
        line-height: 18px;
        text-align: center;
        color: #ffffff;
        padding: 0 3px 5px;
        margin-left: 40px;
        &.active{
          border-bottom: 2px solid #ffffff;
        }
        &:last-of-type{
          font-size: 14px;
          font-family: 'Helvetica';
          padding: 8px 16px;
          border-radius: 17px;
          border: 1px solid #ffffff;
        }
      }
      span{
        position: absolute;
        left: 7%; top: 24px;
        width: 40px;
        height: 2px;
        background-color: #ffffff;
      }
    }
  }
</style>

