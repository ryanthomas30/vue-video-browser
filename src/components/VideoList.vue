<template>
	<ul>
		<VideoListItem
			v-for="video in videos"
			:video="video"
			:key="video.etag"
		>
		</VideoListItem>
	</ul>
</template>

<script>
import VideoListItem from './VideoListItem'

export default {
	name: 'Video List',
	components: {
		VideoListItem
	},
	props: {
		videos: Array
	}
}
</script>

<style>

</style>

