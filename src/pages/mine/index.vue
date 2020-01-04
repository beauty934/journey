<template>
  <div>

    <view class="userinfo">
    <view class="userinfo-avatar">
    <open-data type="userAvatarUrl"></open-data>
    </view>
    <open-data type="userNickName"></open-data>
    </view>
    <i-panel title="武汉我了解，我来推荐！">
      <i-input :value="name" @change="changeName($event)" title="景点" autofocus placeholder="请输入景点" maxlength="20" />
      
      <i-input :value="reason" @change="changeReason($event)" title="推荐理由" placeholder="请输入推荐理由" maxlength="50" />
    </i-panel>
    <i-button @click="handleClick"  hover-class="hover" type="warning" :ghost="true" shape="circle" size="small" >我要推荐</i-button>
    
  </div>
   
</template>

<script>

export default {
  data () {
    return {
      name:"",
      
      reason:""
    }
  },

  methods: {
    changeName (event) {
      this.name = event.mp.detail.detail.value
    },
    changeReason (event) {
      this.reason = event.mp.detail.detail.value
    },
    
    handleClick () {
      if (this.name && this.reason ) {
        wx.showToast({
          title: '推荐了' + this.name,
          icon: 'warning',
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

  created () {
  }
}
</script>

<style scoped>
.userinfo {
  position: relative;
  width: 750rpx;
  height: 320rpx;
  color: #666;
  display: flex;
  flex-direction: column;
  align-items: center;
}
 
.userinfo-avatar {
  overflow:hidden;
  display: block;
  width: 160rpx;
  height: 160rpx;
  margin: 20rpx;
  margin-top: 50rpx;
  border-radius: 50%;
  border: 2px solid #fff;
  box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
}

.bg_box{
    position: absolute;
    bottom: 0;
    right: 0;
    width: 100%;
    height: 100%;
    z-index:-1;
}
.bg_box>image{
    width: 100%;
    height: 100%;
}

.tips {
  padding: 20pt;
  font-size: 10pt;
  color:lightblue;
}
</style>