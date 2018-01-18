<template>
  <div class="m-tabbar">
       <slot></slot>
    </div>
</template>
<script>
import mTabbarItem  from './tabbar-item'
export default {
  props:{
      value:{
          type:String
      }
  },
  computed:{
      valued(){
          return this.$route.matched[0].name;
      }
  }
}
</script>

<style lang="less" scoped>
@import "../assets/less/var.less";
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
            color: @tabbarActiveColor;
        }
    }
}
</style>

