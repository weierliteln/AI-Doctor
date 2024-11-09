<template>
    <view class="login-container">
        <!-- 头像区域 -->
        <view class="avatar-section">
            <image class="avatar" src="https://img.yzcdn.cn/vant/cat.jpeg" mode="aspectFill"></image>
            <text class="welcome">欢迎登录</text>
        </view>

        <!-- 微信登录按钮 -->
        <view class="login-button-section">
            <button class="wechat-login-btn" @click="handleWechatLogin">
                微信一键登录
            </button>
        </view>

        <!-- 协议勾选 -->
        <view class="agreement-section">
            <checkbox-group @change="handleAgreementChange">
                <label class="agreement-label">
                    <checkbox value="1" :checked="isAgree" color="#4080ff" style="transform:scale(0.7)"/>
                    <text class="agreement-text">我已阅读并同意</text>
                    <text class="agreement-link" @click="showAgreement">《用户协议》</text>
                    <text class="agreement-text">和</text>
                    <text class="agreement-link" @click="showPrivacy">《隐私政策》</text>
                </label>
            </checkbox-group>
        </view>

        <!-- 手机号登录入口 -->
        <view class="phone-login-entry" @click="goToPhoneLogin">
            <van-icon name="phone-o" class="phone-icon" />
            <text class="login-text">手机号登录</text>
        </view>
    </view>
</template>

<script>
export default {
    data() {
        return {
            isAgree: false
        }
    },
    methods: {
        handleWechatLogin() {
            if (!this.isAgree) {
                uni.showToast({
                    title: '请先同意用户协议和隐私政策',
                    icon: 'none'
                });
                return;
            }
            // 微信登录逻辑
        },
        handleAgreementChange(e) {
            this.isAgree = e.detail.value.length > 0;
        },
        showAgreement() {
            // 显示用户协议
        },
        showPrivacy() {
            // 显示隐私政策
        },
        goToPhoneLogin() {
            uni.navigateTo({
                url: '/pages/login/phone-login'
            });
        }
    }
}
</script>

<style lang="scss" scoped>
.login-container {
    padding: 0 30px;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.avatar-section {
    margin-top: 120px;
    display: flex;
    flex-direction: column;
    align-items: center;

    .avatar {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        margin-bottom: 20px;
    }

    .welcome {
        font-size: 24px;
        font-weight: bold;
        color: #333;
    }
}

.login-button-section {
    margin-top: 60px;
    width: 100%;

    .wechat-login-btn {
        background-color: #1d3c79;
        color: #fff;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 12px;
        border-radius: 25px;
        border: none;

        .wechat-icon {
            width: 24px;
            height: 24px;
            margin-right: 8px;
        }
    }
}

.agreement-section {
    margin-top: 20px;

    .agreement-label {
        display: flex;
        align-items: center;
        font-size: 14px;
    }

    .agreement-text {
        color: #666;
    }

    .agreement-link {
        color: #4080ff;
    }
}

.phone-login-entry {
    position: fixed;
    bottom: 40px;
    display: flex;
    flex-direction: column;
    align-items: center;
    color: #4080ff;

    .phone-icon {
        font-size: 32px;
        margin-bottom: 8px;
    }

    .login-text {
        font-size: 16px;
    }
}


</style> 