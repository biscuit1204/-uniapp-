<template>
	<view  class="contentItem">
		<scroll-view class="photos" scroll-x="true" enable-flex="true">
			<view class="photosIndex" style="width: (photosList: .length;)*220upx;">
				<view class="userUploadPhotos" v-for="(item, i) in photosList" :key="i"><image :src="item" mode=""></image></view>
				<view class="addPhotosButton" v-if="photosList.length < 9"><image src="../../static/icon/add.svg" mode="" @click="addImg"></image></view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			photosList: []
		};
	},
	methods: {
		addImg() {
			var that = this;
			uni.chooseImage({
				count: 9, //默认9
				sizeType: ['original', 'compressed'], //可以指定是原图还是压缩图，默认二者都有
				sourceType: ['album'], //从相册选择
				success: function(res) {
					// console.log(res.tempFilePaths);
					that.photosList = [...that.photosList, ...res.tempFilePaths];
					that.$emit('myEvent',that.photosList)
				}
			});
		}
	}
};
</script>

<style>
.contentItem {
	width: 675upx;
	font-size: 36upx;
	margin: 30upx 0;
	overflow: hidden;
	white-space: nowrap;
	display: flex;
	flex-direction: column;
}

.photos {
	height: 220upx;
	display: inline-block;
	/* display: flex; */
}
.photosIndex {
	display: flex;
	/* width: 1500upx; */
}
.contentItem image {
	width: 200upx;
	height: 200upx;
	margin: 10upx;
	border-radius: 20upx;
}
.userUploadPhotos {
	height: 220upx;
}
.addPhotosButton {
	width: 180upx;
	height: 180upx;
	margin: 10upx;
	border-radius: 20upx;
	border: #264e70 solid 10upx;
}
.addPhotosButton image {
	width: 160upx;
	height: 160upx;
	/* z-index: 99;	 */
}
</style>
