<template>
	<view class="content">
		<view class="contentndex">
			<view class="contentItem">
				文字上传
				<view class="word"><input type="text" placeholder="上传文字" /></view>
			</view>
			<view class="contentItem">
				图片上传
				<addPhotos @myEvent="getMsg"></addPhotos>
			</view>
			<view class="contentItem">
				视频上传
				<view class="addPhotosButton"><image src="../../static/icon/add.svg" mode="" @click="addVideo"></image></view>
				<video :src="src" v-if="src&&infromation<1" style="width:675upx;height:infromation*675upx;"></video>
				<!-- <video :src="src" v-if="src&&infromation.width<infromation.height"></video> -->
			</view>
		</view>
	</view>
</template>

<script>
import addPhotos from '../../components/addPhotos/addPhotos.vue';
export default {
	data() {
		return {
			photosList: [],
			src: '',
			infromation:''
		};
	},
	methods: {
		getMsg(res) {
			this.photosList = res;
		},
		addVideo() {
			var that = this;
			uni.chooseVideo({
				count: 1,
				sourceType: ['camera', 'album'],
				success: function(res) {
					that.src = res.tempFilePath;
					that.infromation=res.height/res.width
				}
			});
		}
	},
	components: { addPhotos: addPhotos }
};
</script>

<style>
.content {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	color: #264e70;
}
.contentndex {
	width: 675upx;
}
.contentItem {
	width: 675upx;
	font-size: 36upx;
	margin: 30upx 0;
	overflow: hidden;
	white-space: nowrap;
	display: flex;
	flex-direction: column;
}
.contentItem image {
	width: 200upx;
	height: 200upx;
	margin: 10upx;
	border-radius: 20upx;
}
.word {
	margin: 20rpx;
	width: 635upx;
	height: 80upx;
	line-height: 80upx;
	border: 5upx solid #264e70;
	border-radius: 20upx;
	color: #264e70;
}
.word input {
	height: 80upx;
	line-height: 80upx;
	padding-left: 20upx;
}

.contentItem {
	width: 675upx;
	font-size: 36upx;
	margin: 30upx 0;
	overflow: hidden;
	white-space: nowrap;
	display: flex;
	flex-direction: column;
}
.contentItem image {
	width: 200upx;
	height: 200upx;
	margin: 10upx;
	border-radius: 20upx;
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
