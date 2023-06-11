<script>
	import Hoverbutton from './+hoverbutton.svelte';
	let quote = "Get a Quote";
</script>

<div class="quote">
	<a href="/contact">{quote}</a>
</div>

<style>
	.quote {
		position: fixed;
		bottom: 50px;
		right: 0px;
		font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
	}
</style>
