<template>
  <div class="download_btn">
    <div class="btn" @click="iphone_download">
      <img src="../../assets/icon/download_ic_ios.png" alt=""><a href="https://itunes.apple.com/cn/app/kk-gou-wu/id1319173852?mt=8" target="_blank">iPhone</a>
    </div>
    <div class="btn" @click="android_download">
      <img src="../../assets/icon/download_ic_android.png" alt=""><a href="jhttps://download.lanehub.cn/android" target="_blank">Android</a>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    iphone_download(){
      window.open('https://itunes.apple.com/cn/app/kk-gou-wu/id1319173852?mt=8');
    },
    android_download(){
      window.location.href = 'https://download.lanehub.cn/android';
    }
  }
}
</script>
<style lang="less" scoped>
  @media screen and(max-width:1440px){
    .download_btn{
      width: 314px;
      height: 48px;
      .btn{
        float: left;
        margin-right: 33px;
        text-align: center;
        line-height: 48px;
        width: 140px;
        height: 48px;
        border-radius: 27.5px;
        background-color: #000000;
        cursor: pointer;
        &:last-child{
          margin-right: 0;
          img{
            transform: translateY(-2px);
          }
        }
        img{
          width: 20px;
          vertical-align: middle;
          transform: translateY(-3px);
        }
        a{
          margin-left: 10px;
          display: inline-block;
          vertical-align: middle;
          font-family: Helvetica;
          font-size: 16px;
          font-weight: 300;
          letter-spacing: 1px;
          text-align: center;
          color: #ffffff;
        }
      }
    }
  }

  @media screen and(min-width:1440px){
    .download_btn{
      width: 400px;
      // width: 314px;
      height: 55px;
      // height: 48px;
      .btn{
        float: left;
        margin-right: 33px;
        text-align: center;
        line-height: 55px;
        // line-height: 48px;
        width: 171px;
        height: 55px;
        // width: 140px;
        // height: 48px;
        border-radius: 27.5px;
        background-color: #000000;
        cursor: pointer;
        &:last-child{
          margin-right: 0;
          img{
            transform: translateY(-2px);
          }
        }
        img{
          width: 24px;
          // width: 20px;
          vertical-align: middle;
          transform: translateY(-3px);
        }
        a{
          margin-left: 10px;
          display: inline-block;
          vertical-align: middle;
          font-family: Helvetica;
          font-size: 20px;
          // font-size: 16px;
          font-weight: 300;
          letter-spacing: 1px;
          text-align: center;
          color: #ffffff;
        }
      }
    }
  }
</style>

