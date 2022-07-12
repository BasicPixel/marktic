<script type="ts">
	export let value: string;
</script>

<label for="markdown" class="text-lg text-zinc-500">markdown</label>

<textarea
	id="markdown"
	bind:value
	dir="auto"
	class="p-4 mt-2 bg-transparent font-mono w-full max-h-[70h] h-[70vh] text-zinc-300 border zinc-border rounded"
/>
