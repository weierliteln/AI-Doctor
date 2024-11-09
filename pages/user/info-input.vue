<template>
  <view class="info-input">
    <!-- 顶部导航 -->
    <view class="nav-header">
      <van-icon name="arrow-left" @click="goBack" />
      <text>信息录入</text>
    </view>

    <!-- 信息列表 -->
    <view class="info-list">
      <view class="info-item" @click="handleNameClick">
        <text class="label">姓名</text>
        <view class="value-box">
          <text class="placeholder">为更好的服务请输入真实姓名</text>
          <van-icon name="arrow" />
        </view>
      </view>

      <view class="info-item" @click="handleBirthClick">
        <text class="label">出生年月</text>
        <view class="value-box">
          <text class="placeholder">请选择出生日期</text>
          <van-icon name="arrow" />
        </view>
      </view>

      <view class="info-item" @click="handleGenderClick">
        <text class="label">性别</text>
        <view class="value-box">
          <text>女</text>
          <van-icon name="arrow" />
        </view>
      </view>

      <view class="info-item" @click="handleHeightClick">
        <text class="label">身高</text>
        <view class="value-box">
          <text>170cm</text>
          <van-icon name="arrow" />
        </view>
      </view>

      <view class="info-item" @click="handleWeightClick">
        <text class="label">最新体重</text>
        <view class="value-box">
          <text>70kg</text>
          <van-icon name="arrow" />
        </view>
      </view>

      <view class="info-item" @click="handleTargetClick">
        <text class="label">目标体重</text>
        <view class="value-box">
          <text class="placeholder">请选择目标体重</text>
          <van-icon name="arrow" />
        </view>
      </view>
    </view>

    <!-- 底部提示文字 -->
    <view class="bottom-tips">
      可根据您的具体情况随时修改基础信息，在在个人中心中或者再进一步进行诊断后也是能够修改
    </view>
  </view>
</template>

<style lang="scss" scoped>
.info-input {
  min-height: 100vh;
  background-color: #fff;
  padding: 0 16px;
}

.nav-header {
  display: flex;
  align-items: center;
  height: 44px;
  font-size: 16px;
  
  .van-icon {
    margin-right: 8px;
    font-size: 20px;
  }
}

.info-list {
  margin-top: 20px;
}

.info-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 0;
  border-bottom: 1px solid #f5f5f5;

  .label {
    color: #333;
    font-size: 16px;
  }

  .value-box {
    display: flex;
    align-items: center;
    
    .placeholder {
      color: #999;
    }

    .van-icon {
      margin-left: 4px;
      color: #999;
    }
  }
}

.bottom-tips {
  margin-top: 20px;
  padding: 0 16px;
  font-size: 14px;
  color: #999;
  line-height: 1.4;
}
</style>

<script>
export default {
  methods: {
    goBack() {
      uni.navigateBack();
    },
    handleNameClick() {
      // 处理姓名点击
    },
    handleBirthClick() {
      // 处理出生日期点击
    },
    handleGenderClick() {
      // 处理性别点击
    },
    handleHeightClick() {
      // 处理身高点击
    },
    handleWeightClick() {
      // 处理体重点击
    },
    handleTargetClick() {
      // 处理目标体重点击
    }
  }
}
</script> 