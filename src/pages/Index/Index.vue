<template>
  <div>
    <header class="m-header is-fixed is-bg top-search">
      <div class="search-wrap">
        <img src="../../assets/images/ic_search_gray.png" alt="">
        <span class="placeholder">影视 图书 唱片 小组 舞台剧等</span>
        <img src="../../assets/images/ic_scan_gray.png" alt="">
      </div>
      <div class="m-header-button is-right" style="text-align: center;width: 50px;">
        <a href="javascript:;"><img class="m-icon-img" src="../../assets/images/ic_chat_white.png" /></a>
      </div>
    </header>
      <div class="page-content">
            <!-- <m-swipe swipeid="swipe01" :autoplay="1000" effect="cube">
                <div class="swiper-slide slide02" slot="swiper-con">Slide 1</div>
                <div class="swiper-slide slide01" slot="swiper-con">Slide 2</div>
                <div class="swiper-slide slide03" slot="swiper-con">Slide 3</div>
            </m-swipe> -->
            <!-- <m-swipe swipeid="swipe021" :loop="false" paginationType="fraction" :autoplay="2000">
                <div class="swiper-slide slide01" slot="swiper-con">Slide 1</div>
                <div class="swiper-slide slide02" slot="swiper-con">Slide 2</div>
                <div class="swiper-slide slide03" slot="swiper-con">Slide 3</div>
            </m-swipe> -->

      <m-swipe swipeid="swipe01" :autoplay="1000" paginationDirection="right">
        <div class="swiper-slide " slot="swiper-con"><img src="../../assets/images/banner/01.jpg" alt=""></div>
        <div class="swiper-slide " slot="swiper-con"><img src="../../assets/images/banner/02.jpg" alt=""></div>
        <div class="swiper-slide " slot="swiper-con"><img src="../../assets/images/banner/03.jpg" alt=""></div>
      </m-swipe>


      <m-cell title="提醒" icon>
          <img src="../../assets/images/ic_mine_notification.png" alt="" srcset="" slot="icon">
          
          <a href="javascript:;" slot="cell-right">
            <img src="../../assets/images/ic_arrow_gray_small.png" alt="" srcset="">
          </a>
      </m-cell>
      <m-cell title="设置">
          <a href="javascript:;" slot="cell-right">
            <img src="../../assets/images/ic_arrow_gray_small.png" alt="" srcset="">
          </a>
      </m-cell>
      <m-cell title="热门" icon>
          <span slot="icon" class="sp"></span>
          <a href="javascript:;" slot="cell-right">
            <img src="../../assets/images/ic_arrow_gray_small.png" alt="" srcset="">
          </a>
      </m-cell>

      <m-cell-media author="作者：大象公会" column="来自栏目：广播精选" img="https://qnmob2.doubanio.com/img/files/file-1489047494.jpg">
              <span slot="title">个人意见：为什么中国没有鲍勃·迪伦这样的民谣歌手</span>
              <span slot="describe">我们这一代人的成长年代，真正的诗歌课从来都是缺席的。</span>
      </m-cell-media>
      
        </div>
      
  </div>
</template>

<script>
import mHeader from "../../components/header";
import mSwipe from '../../components/swipe'
import mCell from "../../components/cell";
import mCellMedia from "../../components/media-cell"
export default {
  name: "index",
  components: {
    mHeader,
    mSwipe,
     mCell,
    mCellMedia
  },
 
created:function (){
    // var url='/api'
    // this.$axios.get(url)
    // .then(function (response) {
    //   console.log(response);
    // })
    // .catch(function (error) {
    //   console.log(error);
    // });

        var url='/api/movie/in_theaters';
        this.$axios.get(url).then((response)=>{
          console.log(response)
          }).catch((e)=>{
            console.log(e)
          })
}


};
</script>
<style lang="less" scoped>
 @import "../../assets/less/var.less";
.is-fixed ~ .page-content{
margin-top:-14px;
}
#app .m-tabbar{z-index: 999999999999}

 header.m-header {
    padding: 0 0 0 10px;
  }
  
  .is-fixed~.page-content {
    padding-top: 58px;
    // padding-bottom: 50px;
  }
  
  .top-search {
    .search-wrap {
      width: 100%;
      height: 30px;
      background: #fff;
      border-radius: 4px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      color: #c0c0c0;
      padding: 0 12px;
      .placeholder {
        flex: 1;
        text-align: left;
        padding-left: 12px;
      }
      img {
        width: 20px;
        height: 20px;
      }
    }
  }
  
  .hot-wrap,
  .recommend-wrap {
    padding-top: 12px;
  }
  .m-header {
    display: flex;
    align-items: center;
    height: 44px;
    padding: 0 10px;
    background: #fff;
    color: @headerDefaultColor;
    position: relative;
    &:after {
      content: '';
      position: absolute;
      left: 0;
      bottom: 0;
      right: 0;
      height: 1px;
      background: @headerBorderColor;
      transform: scaleY(0.5);
    }
    a {
      color: @headerDefaultColor;
    }
    .m-header-button {
      width: 70px;
      align-items: stretch;
      &.is-left {
        text-align: left;
      }
      &.is-right {
        text-align: right;
      }
      .m-icon-img {
        width: 20px;
        height: 20px;
      }
      .margin-right-10 {
        margin-right: 10px;
      }
    }
    .m-header-title {
      flex: 1;
      text-align: center;
      font-size: 16px;
      text-overflow: ellipsis;
      white-space: nowrap;
      overflow: hidden;
    }
    &.is-bg {
      background: @headerBg;
      color: #fff;
      a {
        color: #fff;
      }
      .m-header-title {
        color: #fff;
      }
      &:after {
        content: '';
        position: absolute;
        left: 0;
        bottom: 0;
        right: 0;
        height: 0px;
        background: @headerBorderColor;
        transform: scaleY(0.5);
      }
    }
    &.is-fixed {
      position: fixed;
      left: 0;
      right: 0;
      top: 0;
      z-index: 9;
    }
  }
</style>


