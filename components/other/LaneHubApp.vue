<template>
  <div class="app">
    <img src="../../assets/img/index_img_02.jpg" alt="">
    <div class="app_box">
      <ImgText :imageText="img_text"></ImgText>
      <DownLoadBtn></DownLoadBtn>
    </div>
  </div>
</template>
<script>
import ImgText from '../public/ImageText';
import DownLoadBtn from '../public/DownLoadBtn';

export default {
  components: {
    ImgText,DownLoadBtn
  },
  data(){
    return {
      img_text: [
        {
          title: ['LANEHUB 瓴里 App'],
          content: [
            {
              desc:[
                '生活达人分享，打开新世界大门，了解品质生活。',
                '和志趣相投的朋友一起讨论，碰撞出改造生活的新灵感。',
                '告诉瓴里你的想法，属于你的梦幻产品即将诞生。',
              ],
            }
          ],
          btn: false,
          btn_text: "",
          btn_her: "",
          img_url: ''
        }
      ]
    }
  }
}
</script>
<style lang="less" scoped>
  .app{
    min-width: 1280px;
    min-height: auto;
    position: relative;
    img{
      width: 100%;
      height: 100%;
      display: block;
    }
    .app_box{
      position: absolute;
      right: 0;top: 19%;
      z-index: 2000;
      width: 780px;
      height: 380px;
      margin-right: 10%;
      .image_text_wrap{
        min-width: 780px;
        max-width: 800px;
        margin-bottom: 90px;
        margin-bottom: 72px;
        margin-top: -96px;
      }
      .download_btn{
        margin: auto;
      }
    }
  }
</style>


