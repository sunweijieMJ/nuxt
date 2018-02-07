<template>
  <footer>
    <!-- <h2>
      <img src="../../assets/icon/footer_ic_logo.png" alt="">
    </h2>
    <div class="tab">
      <a href="javascript:;" v-for="(item,index) in tab" :key="index" @click="chooseTab(item.router)"><span v-if="item.title === '首页'">首页</span>{{item.title}}</a>
    </div> -->
    <p @click="skip">&copy; 2018 LANEHUB·<span>沪ICP备17049047号</span></p>
  </footer>
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
          title: '加入我们',
          router: 'JoinUs',
        }
      ],
    }
  },
  created(){
    this.chooseTab(this.$route.name);
  },
  methods: {
    skip(){
      window.location.href = 'http://www.miibeian.gov.cn/';
    },
    chooseTab(name){
      if(name === 'JoinUs'){
        window.open('https://mp.weixin.qq.com/s/T7gEFB6M4TvBwPVfFZCGiA');
        return;
      }
      this.activeTab = name;
      this.$router.push({name:name});
    },
  }
}
</script>

<style lang="less" scoped>
  @media screen and(max-width:1440px){
    footer{
      min-width: 1280px;
      padding: 80px 0;
      height: 20px;
      color: #ffffff;
      h2{
        img{
          display: block;
          margin: auto;
          width: 154px;
        }
      }
      .tab{
        width: 590px;
        margin: 44px auto 66px;
        a{
          font-size: 14px;
          font-weight: 300;
          line-height: 14px;
          letter-spacing: 1px;
          text-align: center;
          color: #000000;
          margin-right: 71px;
          &:last-child{
            margin-right: 0;
          }
          span{
            color: #ffffff;
            opacity: 0;
            visibility: hidden;
          }
        }
      }
      p{
        cursor: pointer;
        font-size: 14px;
        line-height: 20px;
        letter-spacing: 0.9px;
        text-align: center;
        color: #777777;
        span{
          font-weight: 100;
        }
      }
    }
  }
  @media screen and(min-width:1440px){
    footer{
      min-width: 1280px;
      padding: 105px 0;
      // padding-top: 80px;
      height: 20px;
      // height: 256px;
      color: #ffffff;
      h2{
        img{
          display: block;
          margin: auto;
          width: 154px;
        }
      }
      .tab{
        width: 590px;
        margin: 50px auto 90px;
        // margin: 44px auto 66px;
        a{
          font-size: 14px;
          font-weight: 300;
          line-height: 14px;
          letter-spacing: 1px;
          text-align: center;
          color: #000000;
          margin-right: 71px;
          &:last-child{
            margin-right: 0;
          }
          span{
            color: #ffffff;
            opacity: 0;
            visibility: hidden;
          }
        }
      }
      p{
        cursor: pointer;
        font-size: 14px;
        line-height: 20px;
        letter-spacing: 0.9px;
        text-align: center;
        color: #777777;
        span{
          font-weight: 100;
        }
      }
    }
  }
</style>

