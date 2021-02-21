<template>
<div class="page page-color" >
  <div >
    <mp-searchBar></mp-searchBar>
  </div>
   <!-- 分类 -->
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
    <!-- 招工信息-->
      <ul>
        <li class="vli" >
          <div class="weui-panel weui-panel_access">
          <div class="weui-panel__bd">
            <div class="weui-media-box weui-media-box_text weui-media-box-margin">
              <div class="weui-flex">
              <h4 class="weui-media-box__title">深圳市招电子普工</h4>
              <h4 class="weui-media-box__title  flex-title_gap">280~336元/天</h4>
              </div>
              <div class="weui-flex">
              <h6 class="weui-media-box__title">工作认可度</h6>
                <mp-rate rateValue=4.5 rateClass="weui-rate-20"></mp-rate>
              <h6 class="weui-media-box__title">工作认可度1</h6>
              </div>
              <div class="weui-media-box__desc">工期不限336-280元每天，长白班 盛产电子产品，手 机配件。监控设备，家用扫地机器人等。岗位多临...</div>
            </div>
          </div>
          </div>
        </li>
      </ul>
</div>
</template>

<script>
import mpSearchBar from '../../../src/searchbar';
import mpRate from '../../../src/rate';

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
    mpRate,
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
      font-size: 0.22rem;
      font-weight: bold;
      margin-top: 0.05rem;
    }
  }
}
.weui-media-box-margin {
  margin: 0rem 0.1rem;
}
.flex-title_gap {
  margin-left: 1.75rem;
  color: #d2363b;
}
.weui-rate-20 {
  height: 20px ;
  width: 20px ;
}
</style>
