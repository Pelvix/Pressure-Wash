<script>
	import Hoverbutton from '../../components/+hoverbutton.svelte';
	let isclickedm = false;
	
</script>

<div class />
<div class="screencontain">
	<div class="screen active">
		<div class="screen-image" />
		<button
			on:click={() => {
				isclickedm = !isclickedm;
			}}
			class="screen-overlay"
		/>
		<div class="screen-content">
			<i class="screen-icon fa-brands fa-codepen" />
			<div class="screen-user">
				<span class="name" data-value="CODEPEN">Driveways</span>
				<a class="link" href="/contact" target="_blank">concrete and pavers</a>
				<div class="content-text">
					Lorem, ipsum dolor sit amet consectetur adipisicing elit. Magnam reprehenderit laboriosam
					labore cumque, aperiam fugiat quos reiciendis provident, facere, voluptates voluptatibus
					rerum laborum eligendi voluptas id dolores expedita natus praesentium.
				</div>
			</div>
		</div>
	</div>
</div>

<style>
	:root {
		--background-rgb: 29 30 34;

		--blue-rgb: rgb(255, 255, 255);
		--primary-rgb: var(--blue-rgb);
	}

	.screencontain {
		display: flex;
		flex-wrap: wrap;
		align-items: center;
		justify-content: center;
		gap: 4px;
	}

	.screen {
		margin: 1px;
		width: 500px;
		display: flex;
		border: 6px solid rgb(var(--primary-rgb) / 80%);
		aspect-ratio: 10 / 16;
		border-radius: 1rem;
		background-color: rgb(var(--primary-rgb) / 15%);
		overflow: hidden;
		position: relative;
		z-index: 10;
		background-size: cover;
		background-repeat: no-repeat;
	}

	.screen:after,
	.screen:before {
		content: '';
		height: 5px;
		position: absolute;
		z-index: 4;
		left: 50%;
		translate: -50% 0%;
		background-color: rgb(255, 255, 255);
	}

	.screen:before {
		width: 15%;
		top: 0rem;
		border-bottom-left-radius: 1rem;
		border-bottom-right-radius: 1rem;
	}

	.screen:after {
		width: 25%;
		bottom: 0rem;
		border-top-left-radius: 1rem;
		border-top-right-radius: 1rem;
	}

	@keyframes pan-overlay {
		from {
			background-position: 0% 0%;
		}

		to {
			background-position: 0% -100%;
		}
	}

	.screen-overlay {
		background: linear-gradient(
			rgb(var(--primary-rgb) / 0.15),
			rgb(var(--primary-rgb) / 0.15) 3px,
			transparent 3px,
			transparent 9px
		);
		background-size: 100% 9px;
		height: 100%;
		width: 100%;
		animation: pan-overlay 22s infinite linear;
		position: absolute;
		z-index: 2;
		left: 0px;
		top: 0px;
		border: 2px;
	}

	@keyframes pan-image {
		0% {
			background-position: 36% 42%;
			background-size: 200%;
		}

		20% {
			background-position: 30% 35%;
			background-size: 200%;
		}

		20.0001% {
			/* -- View 2 -- */
			background-position: 60% 85%;
			background-size: 500%;
		}

		40% {
			background-position: 49% 81%;
			background-size: 500%;
		}

		40.0001% {
			/* -- View 3 -- */
			background-position: 80% 42%;
			background-size: 300%;
		}

		60% {
			background-position: 84% 33%;
			background-size: 300%;
		}

		60.0001% {
			/* -- View 4 -- */
			background-position: 0% 0%;
			background-size: 300%;
		}

		80% {
			background-position: 15% 4%;
			background-size: 300%;
		}

		80.0001% {
			/* -- View 5 -- */
			background-position: 80% 10%;
			background-size: 300%;
		}

		100% {
			background-position: 72% 14%;
			background-size: 300%;
		}
	}

	.screen > .screen-image {
		background-image: url('https://grainger-prod.adobecqms.net/content/dam/grainger/gus/en/public/digital-tactics/know-how/hero/SS-KH_ChooseRightPressureWasherForTheJob_KH-HRO.jpg');
		height: 100%;
		width: 100%;
		position: absolute;
		z-index: 1;
		left: 0px;
		top: 0px;
		background-size: 400%;
		background-position: 0% 0%;
		filter: sepia(7%) hue-rotate(0deg);
		opacity: 0.6;
		animation: pan-image 19s linear infinite;
	}

	.screen > .screen-content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-end;
		flex-grow: 1;
		gap: 4rem;
		position: relative;
		z-index: 3;
		margin: 1rem;
		padding-bottom: 6rem;
		border-radius: 0.6rem;
	}

	.screen > .screen-content > .screen-icon {
		color: white;
		font-size: 4rem;
		text-shadow: 0px 0px 0.5rem white;
	}

	.screen > .screen-content > .screen-user {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 3rem;
		position: relative;
	}

	.screen > .screen-content > .screen-user:before,
	.screen > .screen-content > .screen-user:after {
		content: '';
		position: absolute;
		top: 0px;
		background-color: rgb(var(--primary-rgb));
		border-radius: 1rem;
		box-shadow: 0px 0px 8px 3px rgb(var(--primary-rgb) / 60%);
	}

	.screen > .screen-content > .screen-user:before {
		height: 2px;
		width: 50px;
		translate: -20px -1rem;
		opacity: 0.75;
	}

	.screen > .screen-content > .screen-user:after {
		height: 3px;
		width: 30px;
		translate: 26px calc(-1rem - 0.5px);
	}

	.screen > .screen-content > .screen-user > :is(.name, .link) {
		font-family: 'Source Code Pro', monospace;
		color: rgb(255, 255, 255);
		text-align: center;
		text-transform: uppercase;
	}

	.screen > .screen-content > .screen-user > .name {
		position: relative;
		font-size: 4.25rem;
		font-weight: 400;
	}

	.screen > .screen-content > .screen-user > .name:before,
	.screen > .screen-content > .screen-user > .name:after {
		content: '';
		height: 4px;
		width: 4px;
		position: absolute;
		border: 2px solid white;
		border-radius: 2px;
	}

	.screen > .screen-content > .screen-user > .name:before {
		top: 55%;
		right: -1.5rem;
	}

	.screen > .screen-content > .screen-user > .name:after {
		top: 45%;
		left: -1.5rem;
	}

	.screen > .screen-content > .screen-user > .link {
		opacity: 0.8;
		font-size: 1.5rem;
		text-shadow: 0px 0px 0.5rem white;
		font-weight: 400;
		letter-spacing: 0.3rem;
		text-decoration: none;
	}

	.screen > .screen-content > .screen-user > .link:is(:hover, :focus) {
		text-decoration: underline;
	}

	.active {
		width: 95vw;
		height: 95vh;
		margin: 0;
	}
	.screen.active .screen-user {
		align-self: flex-start;
		text-align: left;

		height: 100%;
		width: 100%;
	}

	.content-text {
		margin: auto 50px 5vh 50px;
		max-width: 65vw;
		text-align: center;
		background-color: rgba(240, 248, 255, 0.377);
		border-radius: 15px;
		padding: 15px;
	}
	@media (max-width: 700px) {
		.screen {
			margin-bottom: 0rem;
		}
	}
</style>
