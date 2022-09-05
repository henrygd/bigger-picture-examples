<script>
	import BiggerPicture from 'bigger-picture/svelte';
	import { masonry } from './masonry';
	import { onMount } from 'svelte';

	// import style
	import 'bigger-picture/css';

	// image data
	export let items = [];

	// we define this in onMount so it runs only in browser
	let bp;

	/** click handler */
	function openBiggerPicture(e) {
		e.preventDefault();
		bp.open({
			items: this.parentElement.children,
			el: this,
		});
	}

	onMount(() => {
		// use onMount to define variable so it runs only in the browser
		bp = BiggerPicture({ target: document.body });
	});
</script>

<section use:masonry>
	{#each items as item}
		<a
			on:click={openBiggerPicture}
			href={item.img.split(' ')[0]}
			data-img={item.img}
			data-thumb={item.thumb}
			data-height={item.height}
			data-width={item.width}
			data-alt={item.alt}
		>
			<img src={item.thumb} alt={item.alt} />
		</a>
	{/each}
</section>

<style>
	section {
		margin: 25px 0 35px;
	}
	img {
		max-width: 100%;
		vertical-align: bottom;
	}
</style>
