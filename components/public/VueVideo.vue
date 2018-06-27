<template>
  <div class="video-box" v-if="video">
    <div class="close-box" @click="hide_video"></div>
    <div class="video-player vjs-custom-skin"
      v-video-player:myVideoPlayer="playerOptions"
      :playsinline="true"
      customEventName="customstatechangedeventname"
      @ready="playerReadied"
      @play="onPlayerPlay($event)"
      @pause="onPlayerPause($event)">
    </div>
  </div>
</template>
<script>
  import imageSize from '../../utils/imageSize.js';

  export default {
    props: ['sources', 'poster', 'video'],
    data(){
      return {
        // 播放配置文件
        playerOptions: {
          playbackRates: [0.7, 1.0, 1.5, 2.0], // ETC 播放速度
          width: process.browser ? document.body.clientWidth : 0,
          autoplay: true, // ETC 如果true,浏览器准备好便开始播放
          muted: false, // ETC 默认情况下将会消除任何音频
          loop: false, // ETC 是否循环
          preload: 'auto', // ETC 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
          language: 'en',
          aspectRatio: this.sources.height >= this.sources.width ? '1:1' : `${this.sources.width}:${this.sources.height}`, // ETC 将播放器置于流畅模式,并在计算播放器的动态大小时使用该值
          fluid: true, // ETC 当true时,Video.js player将拥有流体大小
          sources: [ // ETC 资源
            {
              type: 'video/mp4',
              src: this.sources.video_url // ETC 资源url
            }
          ],
          poster: imageSize(this.poster, '690x0'), // ETC 封面地址
          notSupportedMessage: '此视频暂无法播放，请稍后再试', // ETC 允许覆盖Video.js无法播放媒体源时显示的默认信息。
          controlBar: {
            playToggle: false, // ETC 播放按钮
            progressControl: true, // ETC 进度条
            volumePanel: { // 是否显示声音按钮
              inline: false,
              vertical: true
            },
            timeDivider: false, // ETC 时间分割线
            durationDisplay: true, // ETC 总时间
            remainingTimeDisplay: false, // ETC 剩余时间
            fullscreenToggle: true  // ETC 全屏按钮
          }
        },
        keydown: true,
        isplaying: false // ETC 是否在播放
      };
    },
    methods: {
      hide_video() {
        let that = this;
        document.removeEventListener('keydown', that.listenSpace, false);
        that.$emit('from-vueVideo', false);
      },
      // 键盘事件
      keyCode(e) {
        let that = this;
        // 回车符 ASCII码
        const BLANK = 32;
        if(e.keyCode === BLANK){
          e.preventDefault ? e.preventDefault() : window.event.returnValue = false;
          if(that.$el.querySelector('video').paused){
            that.$el.querySelector('video').play();
          } else {
            that.$el.querySelector('video').pause();
          }
        }
      },
      playerReadied(player){
        let that = this;
        player.bigPlayButton.on('click', () => {
          if(that.isplaying){
            player.pause();
          } else {
            player.play();
          }
        });
      },
      // 播放
      onPlayerPlay(player) {
        let that = this;
        that.isplaying = true;
        if(that.keydown) {
          that.keydown = document.addEventListener('keydown', that.keyCode, false);
        }
      },
      // 暂停
      onPlayerPause(player) {
        this.isplaying = false;
      }
    }
  };
</script>
<style lang="less" scoped>
  .video-box{
    position: fixed;
    z-index: 2000;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: #000;
    .close-box{
      width: 25px;
      height: 25px;
      background: url('../../assets/icon/reaction_ic_delete8.png') no-repeat;
      background-size: contain;
      position: absolute;
      z-index: 2000;
      top: 1%;right: 3%;
      cursor: pointer;
      &:hover{
        background: url('../../assets/icon/reaction_ic_delete.png') no-repeat;
        background-size: contain;
      }
    }
    .video-player{
      width: 100%;
      height: 90%;
      position: absolute;
      left: 0;right: 0;top: 0;bottom: 0;
      margin: auto;
    }
  }
</style>
<style lang="less">
  /**
  * 自定义control-bar
  */
  .video-player {
    .vjs-paused{
      /* 播放按钮 */
      .vjs-big-play-button {
        background-image: url('../../assets/icon/video_ic_play.png');
      }
    }
    .vjs-playing{
      /* 暂停按钮 */
      .vjs-big-play-button {
        opacity: 0;
        &:hover{
          opacity: 1;
        }
        background-image: url('../../assets/icon/video_ic_stop.png');
      }
    }
    /* 开始播放按钮不隐藏 */
    .vjs-has-started{
      .vjs-big-play-button{
        display: block;
      }
    }
    /* 暂停inactive隐藏controlBar */
    .vjs-user-inactive .vjs-control-bar {
      // visibility: hidden;
      // opacity: 0;
      // transition: visibility 1.0s, opacity 1.0s;
    }
    /* inactive隐藏play-button */
    .vjs-user-inactive .vjs-big-play-button{
      visibility: hidden;
      opacity: 0;
      transition: visibility 0.3s, opacity 0.3s;
    }
    .video-js {
      /* 播放暂停按钮 */
      .vjs-big-play-button {
        // display: none;
        height: 2em!important;
        width: 2em!important;
        margin-left: -1em!important;
        margin-top: -1em!important;
        border: none 0;
        background-color:transparent;
        background-size: contain;
        .vjs-icon-placeholder:before{
          content: '';
        }
        &:focus{
          background-color:transparent;
        }
      }
      /*************** 按钮排序顺序通过order来控制 ***************/
      .vjs-control-bar {
        position: fixed;
        width: 94%;
        margin: 0 auto;
        background-color:transparent;
        // 播放按钮
        .vjs-play-control {
          order: 0;
        }
        /******************************** 声音 ********************************/
        .vjs-volume-panel{
          display: flex;
          width: 2em;
          order: 6;
          // 声音进度条变细
          .vjs-volume-control{
            width: 2em;
            left: -2em;
            .vjs-volume-bar{
              width: 0.2em!important;
              margin: 1.4em auto;
              background-color: rgba(255, 255, 255, 0.6);
              // 声音进度条颜色改变
              .vjs-volume-level{
                align-self: center;
                width: 0.2em!important;
                background-color: rgba(255, 255, 255, 1);
                &:before{
                  left: -0.4em!important;
                }
              }
            }
          }
          // 静音按钮替换
          .vjs-vol-0{
            align-self: center;
            width: 2em;
            height: 2em;
            padding-left: 0;
            padding-bottom: 0;
            background: url('../../assets/icon/nav_ic_no_voice_white_8.png') no-repeat;
            background-size: contain;
            .vjs-icon-placeholder:before{
              content: '';
            }
            &:hover{
              background: url('../../assets/icon/nav_ic_no_voice_white.png') no-repeat;
              background-size: contain;
            }
          }
          // 不同大小声音按钮替换
          .vjs-vol-1, .vjs-vol-2, .vjs-vol-3{
            align-self: center;
            width: 2em;
            height: 2em;
            padding-left: 0;
            padding-bottom: 0;
            background: url('../../assets/icon/nav_ic_voice_white_8.png') no-repeat;
            background-size: contain;
            .vjs-icon-placeholder:before{
              content: '';
            }
            &:hover{
              background: url('../../assets/icon/nav_ic_voice_white.png') no-repeat;
              background-size: contain;
            }
          }
          // display: none;
        }
        /******************************** 当前时间 ********************************/
        .vjs-current-time {
          order: 1!important;
          width: 2em;
        }
        /******************************** 时间分割线 ********************************/
        .vjs-time-divider {
          // order: 1;
        }
        /******************************** 进度条 ********************************/
        .vjs-progress-control {
          order: 2;
          .vjs-slider {
            background-color: rgba(255, 255, 255, 0.6);
          }
          // 进度条变细
          .vjs-progress-holder{
            height: 0.2em!important;
            .vjs-play-progress{
              background-color: rgba(255, 255, 255, 1);
            }
          }
        }
        /******************************** 分辨率按钮 ********************************/
        .vjs-resolution-button {
          order: 3;
        }
        /******************************** 播放速度 ********************************/
        .vjs-playback-rate {
          display: none;
        }
        /******************************** 总时间 ********************************/
        .vjs-duration {
          width: 2em;
          order: 4!important;
        }
        /******************************** 全屏按钮 ********************************/
        .vjs-fullscreen-control {
          order: 5;
          align-self: center;
          width: 2em;
          height: 2em;
          margin: 0 1em;
          background: url('../../assets/icon/video_ic_fullscreen_8.png') no-repeat;
          background-size: contain;
          // 放大
          &[title="Non-Fullscreen"]{
            background: url('../../assets/icon/video_ic_fullscreen_esc_8.png') no-repeat;
            background-size: contain;
          }
          &[title="Non-Fullscreen"]:hover{
            background: url('../../assets/icon/video_ic_fullscreen_esc.png') no-repeat;
            background-size: contain;
          }
          // 缩小
          .vjs-icon-placeholder:before{
            content: '';
          }
          &:hover{
            background: url('../../assets/icon/video_ic_fullscreen.png') no-repeat;
            background-size: contain;
          }
        }
      }
    }
  }
</style>

