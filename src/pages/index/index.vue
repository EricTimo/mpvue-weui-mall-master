<template>
<div class="page page-color" >
  <div >
    <mpSearchBar></mpSearchBar>
  </div>
   <!-- 商品分类 -->
            <div class="tabs">
                <div class="tab" @click="getList()">
                    <img src="../../../static/images/index/tab_1.png" alt="icon">
                    <p>热卖商品</p>
                </div>
                <div class="tab" @click="getList()">
                    <img src="../../../static/images/index/tab_2.png" alt="icon">
                    <p>小米闪购</p>
                </div>
                <div class="tab" @click="getList()">
                    <img src="../../../static/images/index/tab_3.png" alt="icon">
                    <p>以旧换新</p>
                </div>
                <div class="tab" @click="getList()">
                    <img src="../../../static/images/index/tab_4.png" alt="icon">
                    <p>1分拼团</p>
                </div>
            </div>
</div>
</template>

<script>
import mpSearchBar from '../../components/searchbar';

export default {
  data () {
    return {
      userInfo: {
        nickName: 'mpvue',
        avatarUrl: 'http://mpvue.com/assets/logo.png'
      }
    }
  },

  components: {
    mpSearchBar,
  },

  methods: {
    getList(){

    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped lang='less'>
.page-color {
  background-color: #f0f0f0;
}
.tabs {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;

  width: 100%;
  margin-top: 0.3rem;
  padding: 0 0.1rem;
  .tab {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

    width: 20%;
    &:nth-child(n + 6) {
      margin-top: 0.2rem;
    }
    img {
      width: 0.4rem;
    }
    p {
      color: #999;
      font-size: 0.12rem;
      margin-top: 0.05rem;
    }
  }
}
</style>
