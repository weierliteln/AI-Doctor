<template>
	<view class="home-page">
	  <!-- 顶部区域（包含搜索框、标题和轮播图） -->
	  <view class="header">
		<!-- 搜索框 -->
		<view class="search-box">
		  <van-icon name="calendar-o" size="20px" color="#666" />
		  <view class="search-input">
			<van-icon name="search" color="#999" size="16px" />
			<text class="placeholder">搜索视频、文章等</text>
		  </view>
		  <text class="search-btn">搜索</text>
		</view>

		<text class="title">首页</text>
		
		<!-- 轮播图 -->
		<swiper class="banner" indicator-dots autoplay circular>
		  <swiper-item>
			<view class="banner-item">
			  <view class="banner-content">
				<text class="banner-title">快来参加健康打卡挑战！</text>
				<text class="banner-subtitle">活动时间：09-01 10:00</text>
				<view class="banner-btn">了解更多</view>
			  </view>
			  <image src="https://img.yzcdn.cn/vant/cat.jpeg" mode="aspectFit" class="banner-image"></image>
			</view>
		  </swiper-item>
		</swiper>
	  </view>
  
	  <!-- 健康管理模块 -->
	  <view class="section health-manage">
		<view class="section-header">
		  <text class="section-title">健康管理</text>
		  <text class="more">更多></text>
		</view>
		<view class="icon-grid">
		  <view class="grid-item" v-for="(item, index) in healthIcons" :key="index">
			<view class="icon-bg" :style="{ background: item.color }"></view>
			<text>{{ item.name }}</text>
		  </view>
		</view>
	  </view>
  
	  <!-- 功能卡片 -->
	  <view class="function-cards">
		<view class="card orange">
		  <van-icon name="notes-o" size="24px" color="#fff" />
		  <view class="card-content">
			<text class="card-title">健康档案</text>
			<text class="card-desc">您有新的档案</text>
		  </view>
		</view>
		<view class="card blue">
		  <van-icon name="description" size="24px" color="#fff" />
		  <view class="card-content">
			<text class="card-title">评估报告</text>
			<text class="card-desc">进行健康评估</text>
		  </view>
		</view>
	  </view>
  
	  <!-- 内容列表 -->
	  <view class="content-section">
		<view class="tab-header">
		  <text class="tab active">科普视频</text>
		  <text class="tab">健康文章</text>
		</view>
		<view class="video-list">
		  <view class="video-item" v-for="(item, index) in 6" :key="index">
			<image src="https://img.yzcdn.cn/vant/cat.jpeg" mode="aspectFill"></image>
			<view class="video-info">
			  <image class="avatar" src="https://img.yzcdn.cn/vant/cat.jpeg" mode="aspectFill"></image>
			  <text class="title">视频标题</text>
			</view>
			<view class="video-stats">
			  <text class="stat">1.2w</text>
			  <text class="stat">128</text>
			  <text class="stat">分享</text>
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
		healthIcons: [
		  { name: '智能分析', color: '#FFE4BA' },
		  { name: '用药提醒', color: '#E8F8D0' },
		  { name: '饮食管理', color: '#F5F5F5' },
		  { name: '运动计划', color: '#FFE339' }
		]
	  }
	}
  }
  </script>
  
  <style lang="scss" scoped>
  .home-page {
	min-height: 100vh;
	background: #f5f7fa;
  }
  
  .header {
	background: #4080ff;
	padding: 44px 16px 16px;
	
	.search-box {
	  display: flex;
	  align-items: center;
	  gap: 12px;
	  margin-bottom: 16px;
	  
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
	
	.title {
	  color: #fff;
	  font-size: 18px;
	  font-weight: bold;
	  margin-bottom: 12px;
	  display: block;
	}
	
	.banner {
	  height: 160px;
	  margin-bottom: 16px;
	  
	  .banner-item {
		background: rgba(255, 255, 255, 0.1);
		border-radius: 12px;
		padding: 20px;
		height: 100%;
		display: flex;
		justify-content: space-between;
		align-items: center;
		
		.banner-content {
		  color: #fff;
		  
		  .banner-title {
			font-size: 18px;
			font-weight: bold;
			margin-bottom: 8px;
		  }
		  
		  .banner-subtitle {
			font-size: 14px;
			opacity: 0.8;
			display: block;
			margin-bottom: 12px;
		  }
		  
		  .banner-btn {
			display: inline-block;
			padding: 6px 12px;
			background: rgba(255,255,255,0.2);
			border-radius: 4px;
			font-size: 14px;
		  }
		}
		
		.banner-image {
		  width: 80px;
		  height: 80px;
		}
	  }
	}
  }
  
  .section {
	margin-top: 0;
	padding: 16px;
	background: #fff;
	margin-bottom: 12px;
	
	.section-header {
	  display: flex;
	  justify-content: space-between;
	  align-items: center;
	  margin-bottom: 16px;
	  
	  .section-title {
		font-size: 16px;
		font-weight: bold;
	  }
	  
	  .more {
		color: #999;
		font-size: 14px;
	  }
	}
  }
  
  .icon-grid {
	display: grid;
	grid-template-columns: repeat(4, 1fr);
	gap: 16px;
	
	.grid-item {
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	  
	  .icon-bg {
		width: 48px;
		height: 48px;
		border-radius: 24px;
		margin-bottom: 8px;
	  }
	  
	  text {
		font-size: 14px;
		color: #333;
	  }
	}
  }
  
  .function-cards {
	padding: 0 16px;
	display: grid;
	grid-template-columns: 1fr 1fr;
	gap: 12px;
	margin-bottom: 12px;
	
	.card {
	  padding: 16px;
	  border-radius: 12px;
	  display: flex;
	  align-items: center;
	  
	  &.orange {
		background: #FFA940;
	  }
	  
	  &.blue {
		background: #4080ff;
	  }
	  
	  .card-content {
		margin-left: 12px;
		color: #fff;
		
		.card-title {
		  font-size: 16px;
		  font-weight: bold;
		  margin-bottom: 4px;
		}
		
		.card-desc {
		  font-size: 12px;
		  opacity: 0.8;
		}
	  }
	}
  }
  
  .content-section {
	background: #fff;
	padding: 16px;
	
	.tab-header {
	  display: flex;
	  margin-bottom: 16px;
	  
	  .tab {
		margin-right: 24px;
		font-size: 16px;
		color: #666;
		
		&.active {
		  color: #333;
		  font-weight: bold;
		}
	  }
	}
	
	.video-list {
	  display: grid;
	  grid-template-columns: 1fr 1fr;
	  gap: 12px;
	  
	  .video-item {
		image {
		  width: 100%;
		  height: 120px;
		  border-radius: 8px;
		  margin-bottom: 8px;
		}
		
		.video-info {
		  display: flex;
		  align-items: center;
		  margin-bottom: 8px;
		  
		  .avatar {
			width: 24px;
			height: 24px;
			border-radius: 12px;
			margin-right: 8px;
		  }
		  
		  .title {
			font-size: 14px;
			color: #333;
		  }
		}
		
		.video-stats {
		  display: flex;
		  gap: 16px;
		  
		  .stat {
			color: #999;
			font-size: 12px;
		  }
		}
	  }
	}
  }
  </style>