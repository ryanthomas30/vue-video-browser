<template>
	<div>
		{{ video.snippet.title }}
	</div>
</template>
<script>
export default {
	name: 'VideoListItem',
	props: {
		video: Object,

	}

}
</script>
<style>

</style>
