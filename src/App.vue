<template>
	<div>
		<SearchBar @termChange="onTermChange" ></SearchBar>
		<VideoList />
	</div>
</template>

<script>
import SearchBar from './components/SearchBar'
import VideoList from './components/VideoList'
import axios from 'axios'
const YT_API_KEY = 'AIzaSyBRoBEHByo9FEtEr3L5PLkQdW0qoNGnL_0'

export default {
	name: 'App',
	components: {
		SearchBar,
		VideoList
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
			console.log('resp:', resp)
		}
	}

}
</script>
