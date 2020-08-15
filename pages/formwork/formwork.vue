<template>
	<view class="content"><contentIndex :list="list"></contentIndex></view>
</template>

<script>
import contentIndex from '../../components/item-list/item-list.vue';
export default {
	data() {
		return {
			list: [
				{
					name: '上传',
					Comment: '可以向后台上传图片、视频、音频、文件',
					url: '../../pages/upload/upload'
				},
				{
					name: '瀑布流',
					Comment: '用于展示内容',
					url: '../../pages/waterfall/waterfall'
				},
				// {
				// 	name: '点赞、评论',
				// 	Comment: '对帖子内容进行点赞、评论',
				// 	url: '../../pages/upload/upload'
				// }
			]
		};
	},
	components: { contentIndex: contentIndex },
	methods: {}
};
</script>

<style>
.content {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
}
</style>
