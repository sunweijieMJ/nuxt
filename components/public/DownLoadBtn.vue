<template>
  <div class="download_btn">
    <a href="https://itunes.apple.com/cn/app/kk-gou-wu/id1319173852?mt=8" target="_blank" class="btn">
      <img src="../../assets/icon/download_ic_ios.png" alt="iPhone下载图标"><span>iPhone</span>
    </a>
    <a href="https://download.lanehub.cn/android" class="btn">
      <img src="../../assets/icon/download_ic_android.png" alt="Android下载图标"><span>Android</span>
    </a>
  </div>
</template>
<style lang="less" scoped>
  @media screen and(max-width:1440px){
    .download_btn{
      width: 314px;
      height: 48px;
      a{
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
        span{
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
      height: 55px;
      a{
        float: left;
        margin-right: 33px;
        text-align: center;
        line-height: 55px;
        width: 171px;
        height: 55px;
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
          vertical-align: middle;
          transform: translateY(-3px);
        }
        span{
          margin-left: 10px;
          display: inline-block;
          vertical-align: middle;
          font-family: Helvetica;
          font-size: 20px;
          font-weight: 300;
          letter-spacing: 1px;
          text-align: center;
          color: #ffffff;
        }
      }
    }
  }
</style>

