<template>
	<view class="my-container">
		<!-- 用户信息头部 -->
		<view class="header-section">
			<view class="user-header">
				<view class="user-info">
					<image
						class="avatar"
						mode="aspectFill"
						src="https://img.yzcdn.cn/vant/cat.jpeg"
					/>
					<view class="user-detail">
						<text class="nickname">用户昵称</text>
						<view class="follow-info">
							<text>关注 88</text>
							<text class="separator">|</text>
							<text>粉丝 66</text>
						</view>
					</view>
				</view>
				
				<!-- 添加统计信息 -->
				<view class="stats-container">
					<view class="stats-item">
						<text class="number">12</text>
						<text class="label">文章</text>
					</view>
					<view class="stats-item">
						<text class="number">34</text>
						<text class="label">收藏</text>
					</view>
					<view class="stats-item">
						<text class="number">56</text>
						<text class="label">点赞</text>
					</view>
					<view class="stats-item">
						<text class="number">789</text>
						<text class="label">健康币</text>
					</view>
				</view>
			</view>
		</view>

	

		<!-- 功能模块 -->
		<view class="function-module">
			<view class="grid-container">
				<block v-for="(item, index) in functionList" :key="index">
					<view class="grid-item">
						<view class="icon-wrapper" :class="item.colorClass">
							<van-icon :name="item.icon" size="28px" color="#fff" />
						</view>
						<text class="title">{{item.title}}</text>
					</view>
				</block>
			</view>
		</view>

		<!-- 其他设置 -->
		<view class="other-settings">
			<van-cell-group>
				<van-cell title="我的信息" icon="info-o" is-link size="large" />
				<van-cell title="客服" icon="service-o" is-link size="large" />
				<van-cell title="设置" icon="setting-o" is-link size="large" />
				<van-cell title="帮助与反馈" icon="question-o" is-link size="large" />
			</van-cell-group>
		</view>
	</view>
</template>


<script>
	export default {
		data() {
			return {
				functionList: [
					{ title: '我的档案', icon: 'records', colorClass: 'bg-blue' },
					{ title: '健康评测', icon: 'chart-trending-o', colorClass: 'bg-green' },
					{ title: '我的资料', icon: 'contact', colorClass: 'bg-orange' },
					{ title: '我的医生', icon: 'friends-o', colorClass: 'bg-purple' }
				]
			};
		}
	}
</script>
<style>
.my-container {
	min-height: 100vh;
	background-color: #f7f8fa;
}

.my-container .user-header {
	background-color: transparent;
	margin: 0 12px;
	border-radius: 12px;
	padding: 20px;
}

.my-container .user-header .user-info {
	display: flex;
	align-items: center;
}

.my-container .user-header .user-info .user-detail {
	margin-left: 20px;
}

.my-container .user-header .user-info .user-detail .nickname {
	font-size: 18px;
	font-weight: bold;
	color: #fff;
}

.my-container .user-header .user-info .user-detail .follow-info {
	margin-top: 8px;
	font-size: 14px;
	color: rgba(255, 255, 255, 0.8);
}

.my-container .user-header .user-info .user-detail .follow-info .separator {
	margin: 0 10px;
	color: rgba(255, 255, 255, 0.3);
}

.my-container .function-module {
	margin-top: 12px;
	background-color: #fff;
	padding: 20px;
}

.function-module .grid-container {
	display: flex;
	justify-content: space-between;
}

.function-module .grid-item {
	display: flex;
	flex-direction: column;
	align-items: center;
	width: 25%;
}

.function-module .icon-wrapper {
	width: 48px;
	height: 48px;
	background-color: #f5f6fa;
	border-radius: 12px;
	display: flex;
	align-items: center;
	justify-content: center;
	margin-bottom: 8px;
}

.function-module .title {
	font-size: 14px;
	color: #333;
}

.my-container .other-settings {
	margin-top: 12px;
}

.my-container .user-header .user-info .avatar {
	width: 80px;
	height: 80px;
	border-radius: 50%;
}

.stats-container {
	display: flex;
	justify-content: space-around;
	padding-top: 20px;
	margin-top: 20px;
	border-top: 1px solid rgba(255, 255, 255, 0.2);
}

.stats-item {
	display: flex;
	flex-direction: column;
	align-items: center;
}

.stats-item .number {
	font-size: 24px;
	font-weight: bold;
	color: #fff;
	margin-bottom: 8px;
}

.stats-item .label {
	font-size: 14px;
	color: rgba(255, 255, 255, 0.8);
}

/* 添加顶部渐变背景 */
.header-section {
	background: linear-gradient(180deg, #4bc2f1 0%, #87CEEB 60%, #f7f8fa 100%);
	padding-bottom: 20px;
}

/* 修改用户信息区域样式，移除背景色使渐变透出 */
.user-header {
	background-color: transparent;
	margin: 0 12px;
	border-radius: 12px;
	padding: 20px;
}

/* 修改用户信息文字颜色 */
.user-header .user-info .user-detail .nickname {
	font-size: 18px;
	font-weight: bold;
	color: #fff;
}

.user-header .user-info .user-detail .follow-info {
	color: rgba(255, 255, 255, 0.8);
}

.stats-item .number {
	color: #fff;
}

.stats-item .label {
	color: rgba(255, 255, 255, 0.8);
}

/* 分隔符颜色调整 */
.user-header .user-info .user-detail .follow-info .separator {
	color: rgba(255, 255, 255, 0.3);
}

/* 图标背景色 */
.function-module .icon-wrapper.bg-blue {
	background-color: #4080ff;
}

.function-module .icon-wrapper.bg-green {
	background-color: #42b883;
}

.function-module .icon-wrapper.bg-orange {
	background-color: #ff6b35;
}

.function-module .icon-wrapper.bg-purple {
	background-color: #8a2be2;
}

/* 修改功能模块样式 */
.function-module {
	margin: -10px 12px 12px;  /* 使用负边距让功能模块略微往上 */
	background-color: #fff;
	padding: 20px;
	border-radius: 12px;
}

/* 其他设置样式调整 */
.other-settings :deep(.van-cell) {
    padding: 12px 16px;  /* 增加单元格的内边距 */
}

.other-settings :deep(.van-cell__title) {
    font-size: 16px;  /* 增大标题文字 */
}

.other-settings :deep(.van-icon) {
    font-size: 22px !important;  /* 增大图标尺寸 */
    margin-right: 8px;  /* 增加图标和文字的间距 */
}

.other-settings :deep(.van-cell__right-icon) {
    font-size: 16px !important;  /* 增大右侧箭头图标 */
}
</style>
