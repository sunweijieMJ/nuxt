<template>
  <div class="products">
    <Banner :banner="banner_msg"></Banner>
    <PartnerContent></PartnerContent>
    <DownLoad></DownLoad>
    <LaneHubFooter></LaneHubFooter>
  </div>
</template>
<script>
import Banner from "../components/public/Banner";
import PartnerContent from '../components/other/PartnerContent';
import DownLoad from '../components/public/DownLoad';
import LaneHubFooter from '../components/public/LaneHubFooter';

import banner_url from '../assets/img/cooperate_img_banner.jpg';
import banner_bg_url from '../assets/img/cooperate_img_banner_bg.jpg';

export default {
  components: { Banner, PartnerContent, DownLoad, LaneHubFooter},
  data() {
    return {
      banner_msg: {
        img: banner_url,
        bg_img: banner_bg_url,
        logo: false,
        title: ['Where are you','一起创造新的生活方式'],
        desc: ''
      }
    };
  }
};
</script>
<style lang="less" scoped>
  @import '../assets/style/tool.less';
</style>