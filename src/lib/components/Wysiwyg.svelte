<script lang="ts">
	import hljs from "highlight.js";
	import "highlight.js/styles/github.css";
	import { onMount } from "svelte";

	export let html: string = "";

	let container: HTMLDivElement | null = null;
	let cleanHTML = "";

	function highlight() {
		if (!container) return;

		container.querySelectorAll("pre code").forEach((block) => {
			hljs.highlightElement(block as HTMLElement);
		});
	}

	onMount(async () => {
		const DOMPurify = (await import("dompurify")).default;
		cleanHTML = DOMPurify.sanitize(html);
		highlight();
	});
</script>

<div class="wysiwyg" bind:this={container}>
	{@html cleanHTML}
</div>