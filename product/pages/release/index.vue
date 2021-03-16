<!-- 找活 招工 项目转单 -->
<template>
<div class="container">
    <div class="title">请选择发布类型</div>
    <div class="cartlist">
        <!--  -->
        <div class="item" @click="navigateTo(index)" :data-index="index" v-for="(item,index) in tabs" :key="index">
            <div class="con">
                <div class="center">
                    <div class="img">{{item.name}}
                        <img :src="item.skin" alt="">
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="imgClose" @click="closePage">
        <img :src='closeObj.skin' alt="">
    </div>
</div>
</template>

<script>
export default {
    name: "",
    data() {
        return {
            closeObj: {
                skin: "/static/images/release/btnClose.png",
                url: "/pages/index/main",
            },
            tabs: [{
                    "skin": "/static/images/release/btnExpressJob.png",
                    "url": "/pages/release/expressjob/main"
                },
                {
                    "skin": "/static/images/release/btnFindJob.png",
                    "url": "/pages/release/findjob/main"
                },
                {
                    "skin": "/static/images/release/btnProject.png",
                    "url": "/pages/release/project/main"
                }
            ]
        }
    },
    //生命周期 - 创建完成（访问当前this实例）
    created() {

    },
    //生命周期 - 挂载完成（访问DOM元素）
    mounted() {

    },
    methods: {
        navigateTo(index) {
            console.log("key:" + index+ " url:"+this.tabs[index].url);
            if (index >= 0) {
                wx.navigateTo(this.tabs[index]);
            } 
        },
        closePage() {
            wx.switchTab(this.closeObj);
        }
    },
}
</script>

<style lang="less" scoped>
/* @import url(); 引入css类 */
.container {
  width: 100%;
  text-align: center;

  .title {
    font-size: 33rpx;
    font-weight: bold;
    color: #323131;
  }

  .cartlist {
    background: #fff;
    margin-top: 54rpx;

    .item {
      padding: 20rpx 64rpx;
      position: relative;

      .con {
        display: flex;
        align-items: center;
        justify-content: space-between;
        transition: all 300ms ease;

        .center {
          display: flex;
          align-items: center;

          .img {
            height: 164rpx;
            width: 622rpx;
            display: block;
            background: #f4f4f4;

            img {
              width: 100%;
              height: 100%;
            }
          }
        }
      }
    }
  }

  .imgClose {
    width: 69rpx;
    height: 69rpx;
    display: block;
    background: #f4f4f4;

    img {
      width: 100%;
      height: 100%;
    }
  }
}
</style>
