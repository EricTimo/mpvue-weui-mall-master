<!--工人发布个人技能信息，找工作 -->
<template>
<div>
    <div class="panel__bd">
        <div class="cell_myname">
            <div class="cell_title">我的名字</div>
            <mp-input></mp-input>
            <div class="cell_myname_bottom"></div>
        </div>
        <div v-for="(item2,index2) in pages" :key="index2">
            <div class="cell_title">{{item2.title}}</div>
            <div class="cell">
                <div class="cell_detail">
                    <div class="placeholder">{{item2.placeholder}}</div>
                    <div class="weui-cell__ft weui-cell__ft_in-access placeholder_offsetY"></div>
                </div>
            </div>
        </div>
    </div>
    <div class="cell_introduce">
        <div class="cell_title">自我介绍</div>
        <div class="cell_introduce_desc">
            <textarea  maxlength="150" placeholder="ddd" v-model.lazy="selfDesc"></textarea>
            <div class="weui-textarea-counter cell_desc_counter"><span>0</span>/200</div>
        </div>
    </div>
    <div class="cell_submit">
        <mp-button @click='submitInfo' type="primary" size="large" btnClass="ml15 mr15" >确认发布</mp-button>
    </div>
</div>
</template>

<script>
import mpButton from '../../../../src/button';
import mpInput from '../../../../src/input';
export default {
    components: {
        mpButton,
        mpInput,
    },
    name: "",
    data() {
        return {
            pages: [{
                    title: "我的身份",
                    placeholder: "工人",
                },
                {
                    title: "我的工种",
                    placeholder: "工人",
                },
                {
                    title: "熟练度",
                    placeholder: "请选择你的熟练度",
                },
                {
                    title: "我的期望工作地",
                    placeholder: "请选择你的期望工作地",
                },
            ],
    selfDesc:"",
        }
    },
    //生命周期 - 创建完成（访问当前this实例）
    created() {

    },
    //生命周期 - 挂载完成（访问DOM元素）
    mounted() {

    },
    methods: {
        submitInfo(e) {
          console.log("desc:>> "+this.selfDesc)
        }
    }
}
</script>

<style lang="less" scoped>
/* @import url(); 引入css类 */
.panel__bd {
  padding-left: 39rpx;
  font-weight: bold;

  .cell_myname {
    position: relative;

    .cell_myname_bottom {
      position: absolute;
      left: 0;
      bottom: 0;
      right: 0;
      border-bottom: 1rpx solid #d9d9d9;
      color: #d9d9d9;
    }
  }
}

.cell_title {
  font-size: 28rpx;
  line-height: 27rpx;
  padding-top: 20rpx;
}

.cell {
  position: relative;
  display: -webkit-box;
  display: -webkit-flex;
  display: block;
  -webkit-box-align: center;
  -webkit-align-items: center;
  align-items: center;
  padding-top: 36rpx;
  padding-bottom: 36rpx;

  font-size: 28rpx;

  .cell_detail {
    display: inline;

    .placeholder {
      font-size: 35rpx;
      line-height: 33rpx;
      color: #d0d0d0;
    }

    .placeholder_offsetY {
      position: relative;
      top: -27rpx;
    }
  }
}

.cell:active {
  background-color: #ececec;
}

.cell:first-child:before {
  display: none;
}

.cell:after {
  content: " ";
  position: absolute;
  left: 0;
  bottom: 0;
  right: 0;
  height: 1px;
  border-bottom: 1rpx solid #d9d9d9;
  color: #d9d9d9;
}

.cell_introduce {
  display: block;
  position: relative;
  padding-left: 29rpx;
  padding-top: 39rpx;
  background-color: white;
  font-size: 28rpx;
  font-weight: bold;
  line-height: 27rpx;

  .cell_title {
    color: #000;
    padding-left: 9rpx;
  }

  .cell_introduce_desc {
    width: 95%;
    height: 182rpx;
    background: #f6f6f6;
    border-radius: 9px;
    position: relative;
    margin-top: 25rpx;
    display: block;

    textarea {
      padding-top: 41rpx;
      padding-left: 34rpx;
      font-size: 27rpx;
      font-weight: bold;
      color: #5e5e5e;
      display: block;
      border: 0;
      resize: none;
      background: transparent;
      outline: 0;
      height: 90%;
    }

    .cell_desc_counter {
      position: absolute;
      bottom: 0;
      right: 0;
    }
  }
}

.cell_submit {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 129rpx;
  align-items: center;
  background: #f6f6f6;
}
</style>
