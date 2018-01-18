<template>
<div>
    <m-tabbar v-model="select">
      <m-tabbar-item id='tab1'>
        <img src="../assets/images/ic_tab_home_normal.png" alt="" slot="icon-normal"> 
        <img src="../assets/images/ic_tab_home_active.png" alt="" slot="icon-active"> 
        首页
      </m-tabbar-item>
      <m-tabbar-item id='tab2'>
        <img src="../assets/images/ic_tab_subject_normal.png" alt="" slot="icon-normal"> 
        <img src="../assets/images/ic_tab_subject_active.png" alt="" slot="icon-active">
        书影音
      </m-tabbar-item>
      <m-tabbar-item id='tab3'>
        <img src="../assets/images/ic_tab_status_normal.png" alt="" slot="icon-normal"> 
        <img src="../assets/images/ic_tab_status_active.png" alt="" slot="icon-active">
        广播
      </m-tabbar-item>
      <m-tabbar-item id='tab4'>
          <img src="../assets/images/ic_tab_group_normal.png" alt="" slot="icon-normal"> 
           <img src="../assets/images/ic_tab_group_active.png" alt="" slot="icon-active"> 
        小组
      </m-tabbar-item>
       <m-tabbar-item id='tab5'>
        <img src="../assets/images/ic_tab_profile_normal.png" alt="" slot="icon-normal"> 
        <img src="../assets/images/ic_tab_profile_active.png" alt="" slot="icon-active">
        我的
      </m-tabbar-item>
    </m-tabbar>
  </div>
</template>
<script>
import mTabbar from '../components/tabbar'
import  mTabbarItem  from '../components/tabbar-item.vue'
export default {
  name:'index',
  components:{
      mTabbar,
      mTabbarItem
  },
  data(){
      return{
          select:"tab1"
      }
  }
}
</script>

<style lang="less" scoped>
.m-tabbar{
    display: flex;
    flex-direction: row;
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    width: 100%;
    overflow: hidden;
    height: 50px;
    background: #fff;
    border-top: 1px solid #e4e4e4;
    
    .m-tabbar-item{
      flex: 1;
      text-align: center;
      .m-tabbar-item-icon{
          display: block;
          padding-top: 2px;
          img{
              width: 28px;
              height: 28px;
          }
      }
      .m-tabbar-item-text{
          display: block;
          font-size: 10px;
          color:#949494;
      }
      &.is-active{
          .m-tabbar-item-text{
              color: #42bd56;
          }
      }
  }

    header.m-header {
    padding: 0 0 0 10px;
  }
  
  .is-fixed~.page-content {
    padding-top: 44px;
    padding-bottom: 50px;
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

}
</style>


