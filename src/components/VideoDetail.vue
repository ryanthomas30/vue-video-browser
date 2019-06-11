<template>
	<div v-if="video" class="detail-container" >
		<div class="embed-responsive embed-responsive-16by9" >
			<iframe class="embed-responsive" :src="videoUrl" />
		</div>
		<div class="details" >
			<h4>{{ video.snippet.title }}</h4>
			<p>{{ video.snippet.description }}</p>
		</div>		
	</div>
</template>

<script>
export default {
	name: 'VideoDetail',
	props: {
		video: Object
	},
	computed: {
		videoUrl() {
			const { videoId } = this.video.id
			return `https://www.youtube.com/embed/${videoId}`
		}
	}
}
</script>

<style scoped>
	.detail-container {
		margin-top: 10px;
		margin-bottom: 10px;
		background-color: white;
		border: 1px solid transparent;
		border-radius: 4px;
		box-shadow: 0 1px 3px 0 rgba(21,27,38,.15);
	}

	.details {
		margin-top: 10px;
		margin-bottom: 10px;
		padding: 10px;
	}

	.embed-responsive {
		border-radius: 4px 4px 0px 0px;
	}

	
</style>


