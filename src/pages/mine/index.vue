<template>
    <div>
       <view class="userInfo">
    <!-- <view class="userInfo-avatar"> -->
    <open-data class="userInfo-avatar" type="userAvatarUrl"></open-data>
    <!-- </view> -->
    <open-data type="userNickName"></open-data>
    </view>
    <i-panel title="您的反馈：">
        <i-cell title="您的星评：">
            <i-rate @change="onChange" :value="starIndex">
                {{starIndex}}星
            </i-rate>
        </i-cell>
        <i-input :value="reason" @change="changeReason($event)" title="您的建议：" placeholder="请输入文字" maxlength="100" />
    </i-panel>
    <i-button @click="handleClick" type="info" size="default">提交 </i-button>
    <view class="tips">您的宝贵意见将是我们前进的动力！！！</view>
    </div>
</template>

<script>
export default {
    data() {
        return {
            starIndex:0 ,
            reason:"" 
        }
    },
    methods: {
    onChange(e){
        console.log(e)
        this.starIndex = e.mp.detail.index
    },
    changeReason (event) {
      this.reason = event.mp.detail.detail.value
    },
    handleClick () {
      if (this.starIndex && this.reason) {
        wx.showToast({
          title: '感谢您的建议',
          icon: 'success',
          duration: 2000
        })
        // TODO:将推荐数据提交到云数据库
      } else {
        wx.showToast({
          title: '信息不完整',
          icon: 'none',
          duration: 2000
        })
      }
    }
    },
}
</script>

<style scoped>
.userInfo{
    position: relative;
    width: 750rpx;
    height: 320rpx;
    color: #666;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.userInfo-avatar{
    overflow: hidden;
    display: block;
    width: 160rpx;
    height: 160rpx;
    margin: 20rpx;
    margin-top: 50rpx;
    border-radius: 50%;
    border: 2px solid #fff;
    box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2)
}

.tips {
  padding: 20pt;
  font-size: 10pt;
  color:rgb(19, 179, 201);
}
</style>