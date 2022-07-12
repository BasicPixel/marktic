<script>
	import { marked } from 'marked';

	let text = '';

	async function getReadmeText() {
		const res = await fetch(`https://cdn.jsdelivr.net/gh/basicpixel/marktic/README.md`);
		text = await res.text();
	}

	getReadmeText();
</script>

<svelte:head>
	<title>marktic: the dumbest markdown SSG</title>
</svelte:head>

<div class="max-w-full prose 2xl:prose-xl prose-invert" dir="auto">
	{@html marked(text, { gfm: true })}
</div>
