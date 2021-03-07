<template>
<div class="page page-color">
    <div>
        <mp-searchBar></mp-searchBar>
    </div>
    <!-- 分类 -->
    <div class="tabs">
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
    <div class="notice">
        <div class="divImg">
            <div class="divBox">
                <img id='imgBg' src='../../../static/images/index/notice_bg.png' alt="icon">
                <div class="divNotice">
                    <img id='imgNotice' src="../../../static/images/index/icon_notice.png" alt="icon">
                    <span>{{notice}}</span>
                </div>
            </div>
        </div>
    </div>
    <!-- 招工信息-->
    <scroll-view :scroll-y="true" class="foods-wrapper" @scroll="goodsScrollAct" :scroll-into-view="whereFood">
        <ul>
            <li v-for="(jobInfo, index) in listData" :key="index" :data-id="index" class="liList">
                <div class="weiui-flex jobInfo_class">
                    <div class="weui-flex title_box">
                        <span class="title">深圳市招电子普工</span>
                        <span class="pay">280~336元/天</span>
                    </div>
                    <div class="weui-flex jobRate_box">
                        <div class="jobRate_title">工作认可度</div>
                        <span class="rate-marginleft">
                            <mp-rate rateValue=4.5 rateClass="weui-rate-30"></mp-rate>
                        </span>
                        <span class="rate-score">{{jobInfo.rate}}</span>
                    </div>
                    <div class="jobDesc_box">工期不限336-280元每天，长白班 盛产电子产品，手 机配件。监控设备，家用扫地机器人等。岗位多临...</div>
                    <div class="food-item">
                        <div class="icon">
                            <image :src="jobInfo.icon" />
                        </div>
                        <div class="content">
                            <h2 class="name">{{jobInfo.name}}</h2>
                            <div class="extra">
                                <span class="count">{{jobInfo.phone}}</span>
                                <span class="rating">{{jobInfo.time}}</span>
                            </div>
                        </div>
                        <div class="phoneIcon">
                            <img src="../../../static/images/index/icon_phone.png">
                        </div>
                    </div>
                </div>
            </li>
        </ul>
    </scroll-view>
</div>
</template>

<script>
import mpSearchBar from '../../../src/searchbar';
import mpRate from '../../../src/rate';

export default {
    data() {
        return {
            changeGoods: 'hot',
            whereFood: 'hot',
            userInfo: {
                nickName: 'mpvue',
                avatarUrl: 'http://mpvue.com/assets/logo.png'
            },
            listData: [{
                rate: 4.3,
                icon: ' /static/images/index/icon_main10.png ',
                name: "欧阳娜娜",
                phone: "13800492210",
                time: "10秒之前",
            }, ],
            notice: "如何关注【花卉通】公众号",
        }
    },

    components: {
        mpSearchBar,
        mpRate,
    },

    methods: {
        getList() {

        }
    },

    created() {
        // let app = getApp()
    }
}
</script>

<style lang="less" scoped>
.whitecolor {
  background-color: #fff;
}

.page-color {
  background-color: #f0f0f0;
}

.tabs {
  .whitecolor();
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  width: 100%;
  height: 207rpx;
  box-sizing: border-box;
  padding: 32rpx 32rpx 50rpx;

  .tab {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 25%;

    img {
      width: 100rpx;
      height: 100rpx;
    }

    p {
      color: #333333;
      font-size: 26rpx;
      font-weight: bold;
      margin-top: 8rpx;
    }
  }
}

.notice {
  display: flex;
  box-sizing: border-box;
  width: 100%;
  height: 121rpx;
  margin: 27rpx 0rpx;

  .divImg {
    .whitecolor();
    width: 100%;
    height: 80%;
    display: flex;
    justify-content: center;
    align-items: center;

    .divBox {
      position: relative;

      #imgBg {
        width: 702rpx;
        height: 59rpx;
      }

      .divNotice {
        display: flex;
        flex-direction: row;
        position: absolute;
    align-items: center;
        top: 14rpx;
        left: 45rpx;
        #imgNotice {
          width: 60rpx;
          height: 33rpx;
        }
        span {
          font-size: 23rpx;
          font-weight: bold;
          color: white;
          padding-left: 30rpx;
        }
      }
    }
  }
}

.foods-wrapper {
  .liList {
    padding-bottom: 15rpx;

    .jobInfo_class {
      background-color: white;
      padding-top: 18rpx;
      padding-left: 55rpx;

      .title_box {
        position: relative;

        .title {
          font-size: 30rpx;
          font-weight: bold;
          line-height: 29rpx;
          color: #333333;
        }

        .pay {
          font-size: 30rpx;
          font-weight: bold;
          color: #d2363b;
          position: absolute;
          line-height: 29rpx;
          right: 49rpx;
        }
      }

      .jobRate_box {
        padding-top: 28rpx;
        line-height: 27rpx;
        align-items: center;

        .jobRate_title {
          font-size: 28rpx;
          font-weight: bold;
          color: #333333;
        }

        .rate-marginleft {
          padding-left: 38rpx;
        }

        .rate-score {
          padding-left: 12rpx;
          font-size: 28rpx;
          font-weight: bold;
          color: #ffab35;
        }
      }

      .jobDesc_box {
        padding-top: 23rpx;
        width: 80%;
        font-size: 23rpx;
        color: #808080;
      }
    }
  }

  .food-item {
    margin: 0 0;
    padding: 0 0;
    display: flex;
    flex-direction: row;
    padding-top: 35rpx;

    .icon {
      flex: 0 0;

      image {
        width: 66rpx;
        height: 66rpx;
      }
    }

    .content {
      padding-left: 21rpx;
      display: flex;
      flex-direction: column;

      .name {
        font-size: 28rpx;
        font-weight: bold;
        line-height: 27rpx;
        color: #333333;
      }

      .extra {
        font-size: 23rpx;
        line-height: 19rpx;
        padding-top: 18rpx;
        color: #b3b3b3;

        .rating {
          padding-left: 25rpx;
        }
      }
    }

    .phoneIcon {
      img {
        width: 47rpx;
        height: 47rpx;
      }

      position: absolute;
      padding-top: 18rpx;
      right: 60rpx;
    }
  }
}
</style>
