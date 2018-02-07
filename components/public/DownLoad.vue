<template>
  <div class="download">
    <div class="download_content">
      <img src="../../assets/icon/download_ic_qc.png" alt="下载二维码">
      <div class="platform">
        <h3>即刻体验 <span>瓴里 App</span></h3>
        <DownLoadBtn></DownLoadBtn>
      </div>
    </div>
  </div>
</template>
<script>
import DownLoadBtn from './DownLoadBtn';
export default {
  components: {
    DownLoadBtn
  }
}
</script>

<style lang="less" scoped>
  .download{
    margin-top: 130px;
    min-width: 1080px;
    padding: 100px 0;
    background-color: #f1f2f6;
    .download_content{
      width: 666px;
      height: 180px;
      margin: auto;
      img{
        width: 180px;
        height: 180px;
        float: left;
      }
      .platform{
        float: right;
        h3{
          margin-bottom: 76px;
          font-size: 48px;
          line-height: 48px;
          font-weight: 300;
          letter-spacing: 2.4px;
          text-align: left;
          color: #000000;
          span{
            font-weight: 400;
          }
        }
      }
    }
  }
</style>
