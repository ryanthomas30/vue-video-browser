<template>
	<div class="container" >
		<SearchBar @termChange="onTermChange" />
		<VideoDetail :video="selectedVideo" />
		<VideoList :videos="videos" @videoSelect="onVideoSelect" />
	</div>
</template>

<script>
import SearchBar from './components/SearchBar'
import VideoList from './components/VideoList'
import VideoDetail from './components/VideoDetail'
import axios from 'axios'
const YT_API_KEY = 'AIzaSyBRoBEHByo9FEtEr3L5PLkQdW0qoNGnL_0'

export default {
	name: 'App',
	components: {
		SearchBar,
		VideoList,
		VideoDetail
	},
	data() {
		return {
			videos: [],
			selectedVideo: {}
		}
	},
	methods: {
		async onTermChange(searchTerm) {
			const resp = await axios.get('https://www.googleapis.com/youtube/v3/search', {
				params: {
					key: YT_API_KEY,
					type: 'video',
					part: 'snippet',
					q: searchTerm
				}
			})
			console.log('resp.data.items:', resp.data.items)
			this.videos = resp.data.items
		},
		onVideoSelect(video) {
			this.selectedVideo = video
		}
	}

}
</script>

<style >
	body {
		background-color: #F6F8F9;
	}
</style>

