<script lang="ts">
	import gsap from 'gsap';
	import ScrollTrigger from 'gsap/dist/ScrollTrigger';
	import { onMount } from 'svelte';
	export let image = 'https://cdn.midjourney.com/7f16aa46-c148-45f7-aae2-644d04677912/0_2.webp';
	let clazz: string;
	export let classimg: string;
	export { clazz as class };

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);
		gsap.to('.parallax_img_container', {
			y: 200,
			ease: 'none',
			scrollTrigger: {
				trigger: '.parallax_img_container',
				start: 'top 80%',
				end: 'bottom 50%',
				scrub: true,
				markers: true,
				toggleActions: 'play revese play reverse'
			}
		});
		gsap.fromTo(
			'.img_container',
			{
				y: 0
			},
			{
				y: -200,
				ease: 'power4.out',
				scrollTrigger: {
					trigger: '.parallax_img_container',
					start: 'top 50%',
					end: 'bottom top',
					scrub: true,

					toggleActions: 'play revese play reverse'
				}
			}
		);
	});
</script>

<div class={clazz + ' parallax_img_container overflow-hidden'}>
	<img src={image} class={classimg + ' img_container w-full object-cover'} alt="" />
</div>
