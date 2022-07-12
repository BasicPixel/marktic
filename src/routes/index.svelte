<script type="ts">
	import { marked } from 'marked';
	import Editor from '../../src/components/Editor.svelte';

	let text: string = 'Loading...';

	async function getReadmeText() {
		const res = await fetch(`https://cdn.jsdelivr.net/gh/basicpixel/marktic/README.md`);
		text = await res.text();
	}

	getReadmeText();
</script>

<svelte:head>
	<title>marktic: the dumbest markdown SSG</title>
</svelte:head>

<div class="flex flex-row gap-4 mb-2">
	<div class="flex-1">
		<Editor bind:value={text} />
	</div>

	<div class="flex-1">
		<h2 class="mb-2 text-lg text-zinc-500">preview</h2>

		<div
			class="max-h-[70vh] h-[70vh] overflow-y-auto w-full max-w-full p-4 prose border rounded zinc-border 2xl:prose-xl prose-invert"
			dir="auto"
		>
			{@html marked(text, { gfm: true })}
		</div>
	</div>
</div>

<button
	class="px-6 py-2 text-lg transition-all bg-teal-800 rounded focus:ring ring-teal-500 hover:bg-teal-700"
	>publish</button
>
