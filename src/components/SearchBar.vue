<template>
	<div>
		<input @input="onInput" placeholder="Search" />
	</div>
</template>

<script>
export default {
	name: 'SearchBar',
	methods: {
		onInput(e) {
			this.$emit('termChange', e.target.value)
		}
	}
}
</script>

<style scoped >
	input {
		width: 75%;
		color: #999;
		background-color: #eee;
		border: 1px solid transparent;
		border-radius: 100px;
		padding: 6px 12px;
		transition: all .25s ease-in-out;

	}

	input:focus {
		outline: none;
		color: #666;
		background-color: white;
		box-shadow: 0 1px 3px 0 rgba(21,27,38,.15);
	}

	div {
		text-align: center;
		margin: 20px;
	}
</style>

