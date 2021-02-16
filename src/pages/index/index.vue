<template>
<div class="page page-color" >
  <div >
    <mpSearchBar></mpSearchBar>
  </div>
   <!-- 商品分类 -->
            <div class="tabs tabs-height">
                <div class="tab" @click="getList()">
                    <img src="../../../static/images/index/tab_1.png" alt="icon">
                    <p>找工作</p>
                </div>
                <div class="tab" @click="getList()">
                    <img src="../../../static/images/index/tab_2.png" alt="icon">
                    <p>找工人</p>
                </div>
                <div class="tab" @click="getList()">
                    <img src="../../../static/images/index/tab_3.png" alt="icon">
                    <p>找项目</p>
                </div>
                <div class="tab" @click="getList()">
                    <img src="../../../static/images/index/tab_4.png" alt="icon">
                    <p>工人/或班组</p>
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
  box-sizing: border-box;
  margin-top: 0.3rem;
  padding: 0 0.4rem;
  .tab {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

    width: 25%;
    &:nth-child(n + 6) {
      margin-top: 0.2rem;
    }
    img {
      width: 1rem;
      height: 0.9rem;
    }
    p {
      color: #333333;
      font-size: 0.2rem;
      font-weight: bold;
      margin-top: 0.05rem;
    }
  }
}
</style>
