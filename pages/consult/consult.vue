<template>
	<view class="consult-page">
		<!-- 顶部标题 -->
		<view class="header">
			<text class="title">资询</text>
		</view>

		<!-- 热门话题 -->
		<view class="hot-topics">
			<view class="topic-header">
				<text>热门话题</text>
				<van-icon name="arrow" />
			</view>
			
			<!-- 话题图标列表 -->
			<view class="topic-grid">
				<view class="topic-item" v-for="(item, index) in 8" :key="index">
					<image src="https://img.yzcdn.cn/vant/cat.jpeg" mode="aspectFit"></image>
					<text>智医病</text>
				</view>
			</view>
		</view>

		<!-- 分类标签 -->
		<view class="category-tabs">
			<view 
				v-for="(tab, index) in tabs" 
				:key="index"
				class="tab-item"
				:class="{ active: currentTab === index }"
				@click="switchTab(index)"
			>
				{{ tab }}
			</view>
			<view class="filter-btn">
				<van-icon name="filter-o" size="20px" />
			</view>
		</view>

		<!-- 医生列表 -->
		<view class="doctor-list">
			<view class="doctor-item" v-for="(item, index) in 3" :key="index">
				<image class="avatar" src="https://img.yzcdn.cn/vant/cat.jpeg" mode="aspectFill"></image>
				<view class="info">
					<view class="top-row">
						<text class="name">张英</text>
						<text class="title">二级心理咨询师</text>
						<text class="price">¥400起</text>
					</view>
					<view class="rating">
						<van-rate value="5" size="12" color="#ffd21e" void-icon="star" void-color="#eee" readonly />
						<text class="rating-count">5625条评价</text>
					</view>
					<view class="description">
						光明疗艺大师傅工程工厂这大使馆反对犯得着无法2化上行服份要符合国际水
					</view>
					<view class="tags">
						<text class="tag">总体心理</text>
						<text class="tag">焦虑症</text>
						<text class="tag">总体心理</text>
					</view>
				</view>
			</view>
		</view>

		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabs: ['医生', '护理师', '营养团队'],
				currentTab: 0,
				filters: ['综合', '好评', '咨询', '价格']
			}
		},
		methods: {
			switchTab(index) {
				this.currentTab = index
			}
		}
	}
</script>

<style lang="scss" scoped>
	.consult-page {
		min-height: 100vh;
		background-color: #f5f7fa;
		padding-bottom: 50px;
	}

	.header {
		background: #4080ff;
		padding: 44px 16px 16px;
		color: #fff;
		.title {
			font-size: 18px;
			font-weight: bold;
		}
	}

	.hot-topics {
		background: #4080ff;
		padding: 0 16px 20px;
		
		.topic-header {
			display: flex;
			justify-content: space-between;
			align-items: center;
			color: #fff;
			margin-bottom: 16px;
		}

		.topic-grid {
			display: grid;
			grid-template-columns: repeat(4, 1fr);
			gap: 16px;
			
			.topic-item {
				display: flex;
				flex-direction: column;
				align-items: center;
				
				image {
					width: 40px;
					height: 40px;
					background: #fff;
					border-radius: 8px;
					margin-bottom: 8px;
				}
				
				text {
					color: #fff;
					font-size: 12px;
				}
			}
		}
	}

	.category-tabs {
		display: flex;
		align-items: center;
		background: #fff;
		padding: 12px 16px;
		margin-bottom: 10px;
		
		.tab-item {
			margin-right: 24px;
			color: #666;
			font-size: 14px;
			
			&.active {
				color: #4080ff;
				font-weight: bold;
			}
		}

		.filter-btn {
			margin-left: auto;
		}
	}

	.doctor-list {
		padding: 0 16px;
		
		.doctor-item {
			background: #fff;
			border-radius: 8px;
			padding: 16px;
			margin-bottom: 10px;
			display: flex;
			
			.avatar {
				width: 60px;
				height: 60px;
				border-radius: 30px;
				margin-right: 12px;
			}
			
			.info {
				flex: 1;
				
				.top-row {
					display: flex;
					align-items: center;
					margin-bottom: 8px;
					
					.name {
						font-size: 16px;
						font-weight: bold;
						margin-right: 8px;
					}
					
					.title {
						color: #666;
						font-size: 14px;
					}
					
					.price {
						margin-left: auto;
						color: #ff4d4f;
					}
				}
				
				.rating {
					display: flex;
					align-items: center;
					margin-bottom: 8px;
					
					.rating-count {
						margin-left: 8px;
						color: #999;
						font-size: 12px;
					}
				}
				
				.description {
					color: #666;
					font-size: 14px;
					margin-bottom: 8px;
					line-height: 1.4;
				}
				
				.tags {
					display: flex;
					flex-wrap: wrap;
					
					.tag {
						background: #f5f7fa;
						color: #666;
						padding: 4px 8px;
						border-radius: 4px;
						font-size: 12px;
						margin-right: 8px;
						margin-bottom: 4px;
					}
				}
			}
		}
	}

	.tab-bar {
		position: fixed;
		bottom: 0;
		left: 0;
		right: 0;
		height: 50px;
		background: #fff;
		display: flex;
		align-items: center;
		border-top: 1px solid #eee;
		
		.tab-item {
			flex: 1;
			display: flex;
			flex-direction: column;
			align-items: center;
			color: #999;
			font-size: 12px;
			
			.van-icon {
				font-size: 20px;
				margin-bottom: 4px;
			}
			
			&.active {
				color: #4080ff;
			}
		}
	}
</style>
