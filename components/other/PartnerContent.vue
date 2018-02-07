<template>
  <div class="partner">
    <div class="text_content">
      <h3>共生共赢的发展平台</h3>
      <p>LANEHUB 瓴里，是由顶尖设计师、互联网专家、与资深家具家居供应链管理者，共同创建的生活方式品牌。旨在提供设计感、品质感、愉悦感的产品，为用户创造愉悦的生活方式。加入 LANEHUB 平台，和我们分享创造新世界的激情。</p>
      <a href="mailto:lei.cao@lanehubinc.com">联系我们</a>
    </div>
    <div class="image_content">
      <li v-for="(item,index) in image_content" :key="index">
        <div>
          <img :src="item.img" alt="logo">
        </div>
        <div>
          <h4>{{item.title}}</h4>
          <p v-for="(val,index) in item.desc" :key="index">{{val}}</p>
        </div>
      </li>
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
          desc: ['LANEHUB 整合全球资源，建立高品质供应链体系。','如果你在家具生产管理、工艺、品控、环保方面表现卓越，或在陶瓷、玻璃、金属、纺织等家居用品领域具备高品质生产制造能力，我们期待与你合作，共同升级中国制造。']
        },
        {
          img: cooperate_img_03,
          title: '高端物业',
          desc: ['LANEHUB 空间希望成为用户生活的一部分。2019 年计划全国一、二线城市覆盖体验中心二十家。','我们希望与新颖高端、有文化品位、追求与用户进行更好互动的商业物业，共创全新的线下体验。']
        },
      ]
    }
  }
}
</script>

<style lang="less" scoped>
  .partner{
    min-width: 1000px;
    .text_content {
      color: #000000;
      padding: 130px 0;
      h3{
        font-size: 48px;
        font-weight: 300;
        line-height: 48px;
        letter-spacing: 2.4px;
        text-align: center;
        color: #000000;
      }
      p{
        width: 1080px;
        margin: 70px auto 95px;
        font-size: 24px;
        font-weight: 300;
        line-height: 34px;
        letter-spacing: 1.8px;
        text-align: left;
        color: #000000;
      }
      a{
        display: block;
        margin: auto;
        width: 152px;
        height: 48px;
        border-radius: 24px;
        border: solid 1px #000000;
        font-size: 18px;
        font-weight: 300;
        line-height: 48px;
        letter-spacing: 1.4px;
        text-align: center;
        color: #000000;
      }
    }
    .image_content{
      width: 1080px;
      margin: auto;
      li{
        list-style: none;
        overflow: hidden;
        margin-bottom: 90px;
        &:last-child{
          margin-bottom: 0;
        }
        >div:first-of-type{
          width: 500px;
          height: 344px;
          float: left;
          margin-right: 55px;
          img{
            width: 100%;
          }
        }
        >div:last-of-type{
          float: left;
          h4{
            font-size: 40px;
            font-weight: 300;
            line-height: 40px;
            letter-spacing: 2px;
            text-align: left;
            color: #000000;
            margin: 25px 0 44px;
          }
          p{
            width: 522px;
            font-size: 24px;
            font-weight: 300;
            line-height: 36px;
            letter-spacing: 1.8px;
            text-align: left;
            color: #000000;
          }
        }
      }
    }
  }
</style>

