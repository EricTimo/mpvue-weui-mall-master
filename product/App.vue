<script>
export default {
  created () {
    // 调用API从本地缓存中获取数据
    /*
     * 平台 api 差异的处理方式:  api 方法统一挂载到 mpvue 名称空间, 平台判断通过 mpvuePlatform 特征字符串
     * 微信：mpvue === wx, mpvuePlatform === 'wx'
     * 头条：mpvue === tt, mpvuePlatform === 'tt'
     * 百度：mpvue === swan, mpvuePlatform === 'swan'
     * 支付宝(蚂蚁)：mpvue === my, mpvuePlatform === 'my'
     */

    let logs
    if (mpvuePlatform === 'my') {
      logs = mpvue.getStorageSync({key: 'logs'}).data || []
      logs.unshift(Date.now())
      mpvue.setStorageSync({
        key: 'logs',
        data: logs
      })
    } else {
      logs = mpvue.getStorageSync('logs') || []
      logs.unshift(Date.now())
      mpvue.setStorageSync('logs', logs)
    }
  },
  log () {
    console.log(`log at:${Date.now()}`)
  }
};
</script>

<style lang='less'>
@px2rem:75rem;
.container {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  padding: 200rpx 0;
  box-sizing: border-box;
}
/* common-style */
.mt15 {
  margin-top: 15rpx;
}
.mb15 {
  margin-bottom: 15rpx;
}
.ml15 {
  margin-left: 15rpx;
}
.mr15 {
  margin-right: 15rpx;
}
.padding15 {
  padding: 15rpx;
}
.page-info {
  padding: 15rpx;
}
.flex-center {
  display: flex;
  align-content: center;
}
.page__hd {
  padding: 40rpx;
}
.page__title {
  text-align: left;
  font-size: 20rpx;
  font-weight: 400;
}
.page__desc {
  margin-top: 5rpx;
  color: #888888;
  text-align: left;
  font-size: 14rpx;
}
.page__bd_spacing {
  padding: 0 15rpx;
}
</style>
