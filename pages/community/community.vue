<template>
	<view class="community-page">
		<!-- 顶部标题和搜索框 -->
		<view class="header">
			<text class="title">社区</text>
			<view class="search-box">
				<view class="search-input">
					<van-icon name="search" color="#999" size="16px" />
					<text class="placeholder">搜索图片、文章、视频</text>
				</view>
				<text class="search-btn">搜索</text>
			</view>
		</view>

		<!-- 热门活动 -->
		<view class="hot-activities">
			<text class="section-title">热门活动</text>
			<scroll-view class="activity-scroll" scroll-x>
				<view class="activity-card">
					<text class="activity-title">#谁吃的是星星?</text>
					<text class="activity-count">2000人参与</text>
				</view>
				<view class="activity-card green">
					<text class="activity-title">活动标题</text>
					<text class="activity-count">参与人数</text>
				</view>
				<view class="activity-card blue">
					<text class="activity-title">活动标题</text>
					<text class="activity-count">参与人数</text>
				</view>
			</scroll-view>
		</view>

		<!-- 推荐内容 -->
		<view class="recommend">
			<text class="section-title">推荐</text>
			<view class="post-list">
				<view class="post-item" v-for="(item, index) in 2" :key="index">
					<view class="post-header">
						<image class="avatar" src="https://img.yzcdn.cn/vant/cat.jpeg" mode="aspectFill"></image>
						<text class="username">飞鸟鱼</text>
						<van-icon name="more-o" class="more-icon" />
					</view>
					<view class="post-content">
						<text class="text">微信被好友删除拉黑，依旧可以聊天！我只能说这个方法太好用啦！</text>
						<view class="image-grid">
							<image 
								v-for="(img, imgIndex) in 3" 
								:key="imgIndex"
								src="https://img.yzcdn.cn/vant/cat.jpeg"
								mode="aspectFill"
							></image>
						</view>
					</view>
					<view class="post-footer">
						<text class="tag">娱乐大爆炸</text>
						<view class="actions">
							<text class="count">34</text>
							<text class="count">108</text>
						</view>
					</view>
				</view>
			</view>
		</view>

		<!-- 悬浮发布按钮 -->
		<view class="float-btn">
			<van-icon name="plus" size="24px" color="#fff" />
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
.community-page {
	min-height: 100vh;
	background-color: #f5f7fa;
}

.header {
	background: #4080ff;
	padding: 44px 16px 16px;
	color: #fff;
	.title {
		font-size: 18px;
		font-weight: bold;
		margin-bottom: 12px;
	}
}

.search-box {
	display: flex;
	align-items: center;
	gap: 12px;
	padding-bottom: 16px;

	.search-input {
		flex: 1;
		height: 36px;
		background: #fff;
		border-radius: 18px;
		display: flex;
		align-items: center;
		padding: 0 12px;
		
		.placeholder {
			color: #999;
			font-size: 14px;
			margin-left: 8px;
		}
	}

	.search-btn {
		color: #fff;
		font-size: 14px;
	}
}

.hot-activities {
	padding: 16px;
	margin-bottom: 16px;

	.section-title {
		font-size: 16px;
		font-weight: bold;
		margin-bottom: 12px;
	}

	.activity-scroll {
		white-space: nowrap;
		
		.activity-card {
			display: inline-flex;
			flex-direction: column;
			width: 120px;
			height: 64px;
			background: #7BB9FF;
			border-radius: 8px;
			padding: 12px;
			margin-right: 12px;

			&.green {
				background: #65D1B7;
			}

			&.blue {
				background: #5C9DFF;
			}

			.activity-title {
				color: #fff;
				font-size: 14px;
				margin-bottom: 4px;
			}

			.activity-count {
				color: rgba(255,255,255,0.8);
				font-size: 12px;
			}
		}
	}
}

.recommend {
	padding: 0 16px;

	.section-title {
		font-size: 16px;
		font-weight: bold;
		margin-bottom: 12px;
	}

	.post-item {
		background: #fff;
		border-radius: 8px;
		padding: 16px;
		margin-bottom: 12px;

		.post-header {
			display: flex;
			align-items: center;
			margin-bottom: 12px;

			.avatar {
				width: 32px;
				height: 32px;
				border-radius: 16px;
				margin-right: 8px;
			}

			.username {
				font-size: 14px;
				font-weight: bold;
			}

			.more-icon {
				margin-left: auto;
			}
		}

		.post-content {
			.text {
				font-size: 14px;
				line-height: 1.4;
				margin-bottom: 8px;
			}

			.image-grid {
				display: grid;
				grid-template-columns: repeat(3, 1fr);
				gap: 4px;

				image {
					width: 100%;
					height: 100px;
					border-radius: 4px;
				}
			}
		}

		.post-footer {
			display: flex;
			justify-content: space-between;
			align-items: center;
			margin-top: 12px;

			.tag {
				color: #666;
				font-size: 12px;
			}

			.actions {
				display: flex;
				gap: 16px;

				.count {
					color: #999;
					font-size: 12px;
				}
			}
		}
	}
}

.float-btn {
	position: fixed;
	right: 16px;
	bottom: 80px;
	width: 48px;
	height: 48px;
	background: #4080ff;
	border-radius: 24px;
	display: flex;
	align-items: center;
	justify-content: center;
	box-shadow: 0 2px 8px rgba(64,128,255,0.3);
}
</style>
