<template>
    <view class="phone-login-container">
        <view class="form-section">
            <!-- 手机号输入 -->
            <view class="input-group">
                <van-icon name="phone-o" size="20px" class="input-icon" />
                <input 
                    class="input"
                    type="number"
                    v-model="phone"
                    placeholder="请输入手机号"
                    placeholder-class="placeholder"
                />
            </view>

            <!-- 验证码输入 -->
            <view class="input-group">
                <van-icon name="info-o" size="20px" class="input-icon" />
                <input 
                    class="input"
                    type="number"
                    v-model="code"
                    placeholder="请输入验证码"
                    placeholder-class="placeholder"
                />
                <text 
                    class="code-btn" 
                    :class="{ disabled: counting }"
                    @click="getVerifyCode"
                >
                    {{ codeText }}
                </text>
            </view>

            <!-- 登录按钮 -->
            <button class="login-btn" @click="handleLogin">登录</button>

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
        </view>
    </view>
</template>

<script>
export default {
    data() {
        return {
            phone: '',
            code: '',
            isAgree: false,
            counting: false,
            timer: null,
            countDown: 60
        }
    },
    computed: {
        codeText() {
            return this.counting ? `${this.countDown}s后重新获取` : '获取验证码';
        }
    },
    methods: {
        getVerifyCode() {
            if (this.counting) return;
            if (!this.phone || !/^1[3-9]\d{9}$/.test(this.phone)) {
                uni.showToast({
                    title: '请输入正确的手机号',
                    icon: 'none'
                });
                return;
            }
            
            // 开始倒计时
            this.counting = true;
            this.countDown = 60;
            this.timer = setInterval(() => {
                if (this.countDown > 0) {
                    this.countDown--;
                } else {
                    this.counting = false;
                    clearInterval(this.timer);
                }
            }, 1000);

            // 发送验证码逻辑
        },
        handleLogin() {
            if (!this.isAgree) {
                uni.showToast({
                    title: '请先同意用户协议和隐私政策',
                    icon: 'none'
                });
                return;
            }
            // 登录逻辑
        },
        handleAgreementChange(e) {
            this.isAgree = e.detail.value.length > 0;
        },
        showAgreement() {
            // 显示用户协议
        },
        showPrivacy() {
            // 显示隐私政策
        }
    },
    beforeDestroy() {
        if (this.timer) {
            clearInterval(this.timer);
        }
    }
}
</script>

<style lang="scss" scoped>
.phone-login-container {
    padding: 0 30px;
    min-height: 100vh;
}

.form-section {
    margin-top: 60px;
}

.input-group {
    margin-bottom: 20px;
    background-color: #f8f8f8;
    border-radius: 8px;
    padding: 12px 15px;
    display: flex;
    align-items: center;
}

.input-icon {
    width: 20px;
    height: 20px;
    margin-right: 10px;
}

.input {
    flex: 1;
    font-size: 14px;
}

.placeholder {
    color: #999;
    font-size: 14px;
}

.code-btn {
    color: #133a87;
    font-size: 14px;
    padding: 0 15px;

    &.disabled {
        color: #999;
    }
}

.login-btn {
    width: 100%;
    background-color: #1d3c79;
    color: #fff;
    padding: 12px;
    border-radius: 25px;
    border: none;
    margin-top: 30px;
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
</style> 