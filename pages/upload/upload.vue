<template>
	<view class="content">
		<view class="contentndex">
			<view class="contentItem">
				文字上传
				<view class="word">
					<input type="text" placeholder="上传文字" />
				</view>	
			</view>
			<view class="contentItem">
				图片上传
				<view class="">
									<scroll-view class="photos" scroll-x="true">
					<image src="../../static/icon/commentLogoIconPath.png" mode=""></image>
				</scroll-view>
				</view>

			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		color: #264e70;
	}
.contentndex{
	width: 675upx;
}	
.contentItem{
	width: 675upx;
	font-size: 36upx;
	margin: 30upx 0;
}
.word{
	margin: 20rpx;
	width: 635upx;
	height: 80upx;
	line-height: 80upx;
	border: 5upx solid #264e70;
	border-radius: 20upx;
	color: #264e70;
}
.word input{
	height: 80upx;
	line-height: 80upx;
	padding-left: 20upx;
}
.photos{
	width: 1500upx;
	height: 120upx;
	background-color: #007AFF;
	white-space: nowrap; 
	display: inline-block;
}
</style>
