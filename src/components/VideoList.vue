<template>
	<ul class="list-group" >
		<VideoListItem
			v-for="video in videos"
			:video="video"
			:key="video.etag"
			@videoSelect="onVideoSelect"
		>
		</VideoListItem>
	</ul>
</template>

<script>
import VideoListItem from './VideoListItem'

export default {
	name: 'VideoList',
	components: {
		VideoListItem
	},
	props: {
		videos: Array
	},
	methods: {
		onVideoSelect(video) {
			this.$emit('videoSelect', video)
		}
	}
}
</script>

<style scoped >
	.list-group {
		box-shadow: 0 1px 3px 0 rgba(21,27,38,.15);
		margin-bottom: 24px;
	}
</style>

