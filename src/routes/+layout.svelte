<script>
	import Hoverbutton from '../components/+hoverbutton.svelte';
	import Getquote from '../components/+getquote.svelte';
	import Footer from '../components/+footer.svelte';
	let isclicked = false;
	let isclickedm = false;
</script>

<slot />
<div class="compagnie">
	<div class="cmpborder">
		<span class="cmpname">Lavage Pro Pression</span>
	</div>
</div>

<div class="header">
	<div class="menu">
		<a
			on:click|preventDefault={() => {
				isclicked = !isclicked;
			}}
			href="/"><Hoverbutton key="1" emoji="Quote" /></a
		>
		<div class={isclicked === true ? 'menuing' : ''}>
			<a href="/" class="second"><Hoverbutton key="2" emoji="test" /></a>
		</div>
		<div class="socials" />
	</div>
</div>

<style>
	.compagnie {
		position: fixed;
		top: 0;
		left: 0;
		display: flex;
		justify-content: center;
		align-items: center;
		text-align: center;
		width: 100vw;
		z-index: 14;
		font-family: Georgia, 'Times New Roman', Times, serif;
	}

	.cmpborder {
		font-family: monospace;
		width: 100vw;
		font-size: 5vh;
		background-color: rgb(79, 82, 92);
		padding: 10px;
	}

	.cmpname {
		border: #333;
		border-radius: 15px;
	}
	.header {
		position: absolute;
		top: 0;
		left: 0;
		display: flex;
		justify-content: space-between;
		align-items: center;
		background-color: #333;
		color: #fff;
		z-index: 15;
	}
	.menuing .second {
		visibility: visible;
		transform: translateX(150px);
		opacity: 1;
	}

	.second {
		position: fixed;
		transition: all 5s cubic-bezier(0.19, 1, 0.22, 1);
		transition-delay: 1s;
		opacity: 0;
	}
</style>
