<template>
  <div class="partner">
    <ul>
      <li v-for="(item,index) in image_content" :key="index">
        <img :src="item.img" alt="logo">
        <h4>{{item.title}}</h4>
        <p v-for="(val,index) in item.desc" :key="index">{{val}}</p>
      </li>
    </ul>
    <div class="contact">
      <p>联系我们</p>
      <p><a href="">recruiting.china@lanehub.com</a></p>
    </div>
  </div>
</template>
<script>
import cooperate_img_01 from '../../assets/img/cooperate_img_01.jpg';
import cooperate_img_02 from '../../assets/img/cooperate_img_02.jpg';
import cooperate_img_03 from '../../assets/img/cooperate_img_03.jpg';

export default {
  data(){
    return {
      image_content: [
        {
          img: cooperate_img_01,
          title: '设计师',
          desc: ['如果你有改变世界的想法','如果你有足够的想法支撑你去改变世界','瓴里有许多跟你一样的人','期待你为这个团队增添更多色彩']
        },
        {
          img: cooperate_img_02,
          title: '供应链',
          desc: ['以中国制造，建立全球的供应链体系。','如果你在家具生产以及家居产品领域有优秀的生产能力，','我们愿意和你共同成长。']
        },
        {
          img: cooperate_img_03,
          title: '高端物业',
          desc: ['2019 年计划全国一、二线城市覆盖体验中心 20 家。','如果你是新颖高端、有文化品位、追求','期待与您共创全新的线下体验。']
        },
      ]
    }
  }
}
</script>
<style lang="less" scoped>
  @media screen and(max-width:1440px){
    .partner{
      min-width: 1280px;
      ul{
        margin: 123px auto 0;
        width: 1180px;
        overflow: hidden;
        li{
          float: left;
          width: 380px;
          margin-right: 20px;
          &:last-child{
            margin-right: 0;
          }
          img{
            display: block;
            width: 380px;
            height: 380px;
          }
          h4{
            font-size: 36px;
            font-weight: 300;
            line-height: 36px;
            letter-spacing: 2px;
            text-align: left;
            color: #000000;
            margin: 50px 0 43px;
          }
          p{
            font-size: 20px;
            font-weight: 300;
            line-height: 34px;
            letter-spacing: 1.5px;
            text-align: left;
            color: #000000;
          }
        }
      }
      .contact{
        padding-top: 130px;
        margin: auto;
        p{
          font-size: 24px;
          line-height: 34px;
          letter-spacing: 1.8px;
          text-align: center;
          font-weight: 300;
          color: #000000;
          a{
            font-size: 24px;
            line-height: 24px;
            letter-spacing: 1.8px;
            text-align: center;
            color: #197bce;
          }
        }
      }
    }
  }
  @media screen and(min-width:1440px){
    .partner{
      min-width: 1280px;
      ul{
        margin: 123px auto 0;
        width: 1180px;
        overflow: hidden;
        li{
          float: left;
          width: 380px;
          margin-right: 20px;
          &:last-child{
            margin-right: 0;
          }
          img{
            display: block;
            width: 380px;
            height: 380px;
          }
          h4{
            font-size: 48px;
            font-weight: 300;
            line-height: 48px;
            letter-spacing: 2px;
            text-align: left;
            color: #000000;
            margin: 50px 0 43px;
          }
          p{
            font-size: 24px;
            font-weight: 300;
            line-height: 34px;
            letter-spacing: 1.5px;
            text-align: left;
            color: #000000;
          }
        }
      }
      .contact{
        padding-top: 130px;
        margin: auto;
        p{
          font-size: 24px;
          line-height: 34px;
          letter-spacing: 1.8px;
          text-align: center;
          font-weight: 300;
          color: #000000;
          a{
            font-size: 24px;
            line-height: 24px;
            letter-spacing: 1.8px;
            text-align: center;
            color: #197bce;
          }
        }
      }
    }
  }
</style>

