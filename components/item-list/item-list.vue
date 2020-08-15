<template>
	<view>
		<view class="contentIndex">
			<view class="contentItem" v-for="(item, i) in list" :key="i" @click="navigator(item.url)">
				<view class="contentItemLeft">
					<view class="contentItemLeftName">{{ item.name }}</view>
					<view class="contentItemTopComment">{{ item.Comment }}</view>
				</view>
				<view class="contentItemRight"><image src="../../static/icon/goItem.png" mode=""></image></view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	props: ['list'],
	data() {
		return {};
	},
	methods: {
		navigator(url) {
			console.log(url);
			uni.navigateTo({
			    url
			});
		}
	}
};
</script>

<style>
.contentIndex {
	width: 675upx;
}
.contentItem {
	width: 675upx;
	height: 160upx;
	margin: 40upx 0;
	background-color: #fdebd3;
	border-radius: 20upx;
	display: flex;
	justify-content: space-between;
	box-shadow: 5px 5px 3px #bbd4ce;
}
.contentItemLeft {
	height: 160upx;
	margin-left: 30upx;
	padding: 20upx 0;
	color: #264e70;
}
.contentItemLeftName {
	height: 60upx;
	line-height: 60upx;
	font-size: 36upx;
}
.contentItemTopComment {
	height: 60upx;
	line-height: 60upx;
	font-size: 28upx;
}
.contentItemRight {
	height: 160upx;
	margin: 40upx 20upx 40upx 0;
	width: 80upx;
}
.contentItemRight image {
	height: 80upx;
	width: 80upx;
}
</style>
