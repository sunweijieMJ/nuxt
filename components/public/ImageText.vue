<template>
  <div class="image_text_wrap">
      <div class="image_text_content" v-for="(item,index) in imageText" :key="index">
        <div class="title">
          <h3 v-for="(val,index) in item.title" :key="index">{{val}}</h3>
        </div>
        <div class="desc" v-for="(item,index) in item.content" :key="index">
          <p v-for="(val,index) in item.desc" :key="index">{{val}}</p>
        </div>
        <div class="btn_wrap" v-if="item.btn">
            <a :href="item.btn_href" @click="skip(item.btn_href)">{{item.btn_text}}</a>
        </div>
        <div class="img_wrap" v-if="item.img_url">
            <img :src="item.img_url" alt="">
        </div>
      </div>
  </div>
</template>
<script>
export default {
  props:['imageText'],
  methods: {
    skip(name){
      this.$router.push({name:name});
    }
  }
};
</script>
<style lang="less" scoped>
  @media screen and(max-width:1440px){
    .image_text_wrap{
      min-width: 1280px;
      .image_text_content {
        color: #000000;
        padding-top: 96px;
        .title{
            margin-bottom: 44px;
          h3 {
            font-size: 36px;
            letter-spacing: 1.8px;
            font-weight: 300;
            font-style: normal;
            line-height: 50px;
            text-align: center;
          }
        }
        .desc{
          margin-bottom: 24px;
          p{
            font-size: 20px;
            font-weight: 300;
            letter-spacing: 1.5px;
            line-height: 34px;
            text-align: center;
          }
        }
        .btn_wrap {
          margin: 72px 0 102px;
          a {
            display: block;
            margin: auto;
            width: 112px;
            height: 36px;
            border-radius: 24px;
            border: solid 1px #000000;
            font-size: 14px;
            font-weight: 300;
            line-height: 36px;
            text-align: center;
            color: #000000;
          }
        }
        .img_wrap {
          margin: 91px auto 0 auto;
          min-width: 1280px;
          min-height: auto;
          img {
            width: 100%;
            height: 100%;
            display: block;
          }
        }
      }
    }
  }
  @media screen and(min-width:1440px){
    .image_text_wrap{
      min-width: 1440px;
      .image_text_content {
        color: #000000;
        padding-top: 124px;
        // padding-top: 96px;
        .title{
            margin-bottom: 56px;
            // margin-bottom: 44px;
          h3 {
            font-size: 48px;
            // font-size: 36px;
            font-weight: 300;
            font-style: normal;
            letter-spacing: 2.4px;
            line-height: 60px;
            // line-height: 50px;
            text-align: center;
          }
        }
        .desc{
          margin-bottom: 34px;
          // margin-bottom: 24px;
          p{
            font-size: 24px;
            // font-size: 20px;
            font-weight: 300;
            line-height: 40px;
            letter-spacing: 1.8px;
            // line-height: 34px;
            text-align: center;
          }
        }
        .btn_wrap {
          margin: 82px 0 130px;
          // margin: 72px 0 102px;
          a {
            display: block;
            margin: auto;
            width: 152px;
            height: 48px;
            // width: 112px;
            // height: 36px;
            border-radius: 24px;
            border: solid 1px #000000;
            font-size: 18px;
            // font-size: 14px;
            font-weight: 300;
            line-height: 48px;
            // line-height: 36px;
            text-align: center;
            color: #000000;
          }
        }
        .img_wrap {
          margin: 122px auto 0 auto;
          // margin: 91px auto 0 auto;
          min-width: 1280px;
          min-height: auto;
          img {
            width: 100%;
            height: 100%;
            display: block;
          }
        }
      }
    }
  }
</style>
