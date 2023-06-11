<script>
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	export let emoji;
	export let key = 0;
	let button;

	class HoverButton {
		constructor(el) {
			this.el = el;
			this.hover = false;
			this.calculatePosition();
			this.attachEventsListener();
		}

		attachEventsListener() {
			window.addEventListener('mousemove', (e) => this.onMouseMove(e));
			window.addEventListener('resize', (e) => this.calculatePosition(e));
		}

		calculatePosition() {
			gsap.set(this.el, {
				x: 0,
				y: 0,
				scale: 1
			});
			const box = this.el.getBoundingClientRect();
			this.x = box.left + box.width * 0.5;
			this.y = box.top + box.height * 0.5;
			this.width = box.width;
			this.height = box.height;
		}

		onMouseMove(e) {
			let hover = false;
			let hoverArea = this.hover ? 0.7 : 0.5;
			let x = e.clientX - this.x;
			let y = e.clientY - this.y;
			let distance = Math.sqrt(x * x + y * y);
			if (distance < this.width * hoverArea) {
				hover = true;
				if (!this.hover) {
					this.hover = true;
				}
				this.onHover(e.clientX, e.clientY);
			}

			if (!hover && this.hover) {
				this.onLeave();
				this.hover = false;
			}
		}

		onHover(x, y) {
			gsap.to(this.el, {
				x: (x - this.x) * 0.4,
				y: (y - this.y) * 0.4,
				scale: 1.15,
				ease: 'power2.out',
				duration: 0.4
			});
			this.el.style.zIndex = 10;
		}
		onLeave() {
			gsap.to(this.el, {
				x: 0,
				y: 0,
				scale: 1,
				ease: 'elastic.out(1.2, 0.4)',
				duration: 0.7
			});
			this.el.style.zIndex = 1;
		}
	}
	onMount(() => {
		const btn1 = document.getElementById(key);
		button = btn1;
		console.log('btn')
		console.log(btn1);
		new HoverButton(button);

	});
</script>

<button id={key}>{emoji}</button>

<style lang="scss">
	button {
		position: fixed;
		border-radius: 50%;
		border: 5px solid white;
		text-decoration: white;
		font-family: Verdana;
		font-weight: bold;
		font-size: 1.25rem;
		backdrop-filter:invert(100%);
		z-index: 15;
		cursor: pointer;
		background: #dde6ebab;
		height: 100px;
		width: 100px;
		opacity: 0.8;
		border: 0px solid #3d94ff00;
		border-radius: 51% 49% 48% 52% / 62% 44% 56% 38%;
		box-shadow: 0px 30px 16px #0c87a300, -40px 60px 32px #00000071, inset -6px 6px 10px #000505c5, inset 2px 6px 10px #000000, inset 20px -20px 22px white, inset 40px -40px 44px #88898a;
	}
	button::after {
		content: '';
		position: absolute;
		background: #e6fdfb;
		height: 20px;
		width: 20px;
		border-radius: 40% 52% 40% 50% / 30% 50% 50% 64%;
		right: 20%;
		top: 20px;
		box-shadow: 30px 10px 0 -25px white;
		opacity: 0.8;
		z-index: 15;
	}
	

</style>
