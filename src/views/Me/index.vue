<template>
  <div class="page-me">
    <div class="cover">
      <navigator></navigator>
      <div class="banner">
        <div class="avatar component_avatar mine-avatar">
          <img src="//img.manhua.weibo.com/static/b/vcomic-h5/dist/img/avatar.78577bb7.png" />
          <!---->
        </div>
        <p Pclass="mine-nickname">click me to login</p>
        <p class="mine-vcoin">My Score: 0</p>
      </div>
    </div>

    <div class="mine-list">
                <item
                v-for="(item, index) in list"
                :key="index"
                :name="item.name"
                :icon="item.icon"
                ></item>
    </div>
    <!---->
  </div>
</template>

<script>
import Navigator from '@/components/Navigator'
import Item from './componments/item'
export default {
  name: 'Me',
  components: {
    Navigator,
    Item
  },
  data () {
    return {
      list: [{ name: 'buy', icon: 'icon-qianbi' },
        { name: 'follow', icon: 'icon-follow' },
        { name: 'history', icon: 'icon-lishi' },
        { name: 'comments', icon: 'icon-yijian' },
        { name: 'articles', icon: 'icon-bought' },
        { name: 'manage', icon: 'icon-zidonggoumai' }
      ]
    }
  }
}
</script>
<style lang="scss" scoped>
.page-me {
  width: 100%;
  height: 100%;
  .cover {
    background: url('../../assets/img/background.png') 100% 100% no-repeat;
    height: 224px;
    width: 100%;
    position: relative;
    &::after {
      position: absolute;
      content: '';
      width: 100%;
      height: 20px;
      left: 0;
      bottom: -1px;
      background-image: url('../../assets/img/cover.png');
      background-size: 100% 100%;
      background-repeat: no-repeat;
    }
    .banner {
      height: 184px;
      margin: 0 auto;
      padding: 34px 40px 0;
      text-align: center;
      .avatar {
        height: 88px;
        width: 88px;
        border-radius: 50%;
        margin: 0 auto;
        img {
          width: 100%;
          height: 100%;
        }
      }
      .mine-nickname {
        color: #fff;
        height: 36px;
        width: 295px;
        font-size: 16px;
        line-height: 36px;
      }
      .mine-vcoin {
        font-size: 14px;
        color: #fff;
        height: 18px;
        line-height: 18px;
        width: 295px;
      }
    }
  }

}
</style>
