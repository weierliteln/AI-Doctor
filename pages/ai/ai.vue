<template>
	<view class="ai-page">
		<!-- 顶部导航 -->
		<view class="nav-header">
			<view class="left">
				<van-icon name="arrow-left" color="#fff" size="20px" />
				<text>AI问诊</text>
			</view>
			<van-icon name="ellipsis" color="#fff" size="20px" />
		</view>

		<!-- AI头像和介绍 -->
		<view class="ai-intro">
			<image class="ai-avatar" src="https://img.yzcdn.cn/vant/cat.jpeg" mode="aspectFit" />
			<view class="ai-message">
				主人，关于您遇到的健康问题，我都可以帮您解答哦~
			</view>
		</view>

		<!-- 常见问题卡片 -->
		<view class="qa-card">
			<view class="card-title">
				<van-icon name="chat-o" color="#4080ff" size="18px" />
				<text>常见问题</text>
			</view>
			<view class="qa-list">
				<text>早餐吃什么？</text>
				<text>中餐吃什么？糖醋排骨？红烧里脊？...</text>
				<text>晚餐吃什么？糖醋排骨？红烧里脊？...</text>
				<text>夜宵吃什么？糖醋排骨？红烧里脊？...</text>
			</view>
		</view>

		<!-- 底部功能区 -->
		<view class="bottom-section">
			<!-- 快捷功能 -->
			<view class="quick-actions">
				<view class="action-item">
					<text>五分钟了解饮食</text>
				</view>
				<view class="action-item">
					<text>找咨询团队</text>
				</view>
				<view class="action-item">
					<text>如何健身</text>
				</view>
			</view>

			<!-- 输入框区域 -->
			<view class="input-section">
				<view class="input-box">
					<text class="placeholder">有问题可以直接向我提哦</text>
				</view>
				<view class="send-btn">
					<van-icon name="plus" color="#666" size="24px" />
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss" scoped>
	.ai-page {
		min-height: 100vh;
		background: linear-gradient(180deg, #4bc2f1 0%, #87CEEB 20%, #f7f8fa 100%);
		padding-bottom: 100px; // 为底部留出空间
	}

	.nav-header {
		padding: 44px 16px 16px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		
		.left {
			display: flex;
			align-items: center;
			gap: 8px;
			color: #fff;
			font-size: 16px;
		}
	}

	.ai-intro {
		padding: 20px;
		display: flex;
		align-items: flex-start;
		gap: 12px;
		
		.ai-avatar {
			width: 48px;
			height: 48px;
			border-radius: 24px;
			background: #fff;
		}
		
		.ai-message {
			background: #fff;
			padding: 12px 16px;
			border-radius: 16px;
			border-top-left-radius: 4px;
			font-size: 14px;
			color: #333;
			max-width: 80%;
		}
	}

	.qa-card {
		margin: 20px 16px;
		background: #fff;
		border-radius: 12px;
		padding: 16px;
		
		.card-title {
			display: flex;
			align-items: center;
			gap: 8px;
			margin-bottom: 12px;
			font-size: 16px;
			font-weight: bold;
		}
		
		.qa-list {
			display: flex;
			flex-direction: column;
			gap: 12px;
			
			text {
				color: #666;
				font-size: 14px;
			}
		}
	}

	.bottom-section {
		position: fixed;
		bottom: 0;
		left: 0;
		right: 0;
		background: #fff;
		padding: 12px 16px;
		
		.quick-actions {
			display: flex;
			justify-content: space-around;
			margin-bottom: 12px;
			
			.action-item {
				color: #666;
				font-size: 14px;
			}
		}
		
		.input-section {
			display: flex;
			align-items: center;
			gap: 12px;
			
			.input-box {
				flex: 1;
				background: #f5f5f5;
				height: 40px;
				border-radius: 20px;
				padding: 0 16px;
				display: flex;
				align-items: center;
				
				.placeholder {
					color: #999;
					font-size: 14px;
				}
			}
			
			.send-btn {
				width: 40px;
				height: 40px;
				background: #f5f5f5;
				border-radius: 20px;
				display: flex;
				align-items: center;
				justify-content: center;
			}
		}
	}
</style>
