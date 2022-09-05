<script lang="ts">
	import BiggerPicture from 'bigger-picture/svelte';

	// import style
	import 'bigger-picture/css';

	// image data
	export let items: any[] = [];

	// we can use directly in a use action
	function openBpInline(target: HTMLElement) {
		const bp = BiggerPicture({
			target,
		});
		bp.open({
			items,
			inline: true,
			noClose: true,
			scale: 1,
			intro: 'fadeup',
		});
	}
</script>

<div use:openBpInline />

<style>
	div {
		position: relative;
		background: #444;
		aspect-ratio: 3/2;
	}
</style>
