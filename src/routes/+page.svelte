<script>
	import Hoverbutton from '../components/+hoverbutton.svelte';
	let screen1 = false;
	let isclickedm2 = false;
	let isclickedm3 = false;
	let current = 'not';
</script>

<body>
	<div class="screencontain">
		<div class="screen active">
			<div class="screen-image" />
			<div class="screen-overlay" />
			<button
				class={current === 'screen-content' ? 'active1' : ''}
				on:click={() => {
					current = 'screen1';
				}}
			>
				<i class="screen-icon fa-brands fa-codepen" />
				<div class="screen-user">
					<span class="name" data-value="CODEPEN">Driveways</span>
					<span class="link">concrete and pavers</span>
					<div class={current === 'content-text' ? 'active' : ''}>
						Lorem, ipsum dolor sit amet consectetur adipisicing elit. Magnam reprehenderit
						laboriosam labore cumque, aperiam fugiat quos reiciendis provident, facere, voluptates
						voluptatibus rerum laborum eligendi voluptas id dolores expedita natus praesentium.
					</div>
				</div>
			</button>
		</div>
		<div class="screen">
			<div class="screen-image2" />
			<div class="screen-overlay" />
			<button
				on:click={() => {
					isclickedm2 = !isclickedm2;
				}}
				class="screen-content"
			>
				<div class="screen-user">
					<span class="name" data-value="CODEPEN">Sidings</span>
					<span class="link">Canexel and Vinyl</span>
				</div>
			</button>
		</div>

		<div class="screen">
			<div class="screen-image3" />
			<div class="screen-overlay" />
			<button
				on:click={() => {
					isclickedm3 = !isclickedm3;
				}}
				class="screen-content"
			>
				<div class="screen-user">
					<span class="name" data-value="CODEPEN">Wood</span>
					<span class="link">restauration and more</span>
				</div>
			</button>
		</div>
	</div>
</body>

<style>
	:root {
		--background-rgb: 29 30 34;

		--blue-rgb: rgb(255, 255, 255);
		--primary-rgb: var(--blue-rgb);
	}
	body {
		height: 90vh;
		background-color: rgb(var(--background-rgb));
		margin: 1rem;
		padding-top: 1.2rem;
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
		border: 8px solid rgb(var(--primary-rgb) / 80%);
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

	.screen > .screen-image2 {
		background-image: url('https://www.housedigest.com/img/gallery/20-incredibly-satisfying-pressure-washing-before-and-after-photos/intro-1654682192.jpg');
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

	.screen > .screen-image3 {
		background-image: url('data:image/jpeg;base64,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');
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
		margin: 0.2rem;
		padding-bottom: 6rem;
		border-radius: 0.6rem;
		background-color: transparent;
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
	.screen.active1 .screen-user {
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
