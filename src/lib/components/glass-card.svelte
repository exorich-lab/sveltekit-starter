<script lang="ts">
	import type { Snippet } from 'svelte';
	import { cn } from '$lib/utils.js';

	let {
		class: className = '',
		glow = false,
		children
	}: {
		class?: string;
		glow?: boolean;
		children?: Snippet;
	} = $props();
</script>

<div
	class={cn(
		'relative overflow-hidden rounded-2xl border border-border/80 bg-background/70 shadow-sm backdrop-blur-xl dark:bg-background/40',
		className
	)}
>
	{#if glow}
		<div
			aria-hidden="true"
			class="pointer-events-none absolute inset-0 bg-[radial-gradient(60%_50%_at_50%_0%,hsl(var(--primary)/0.12),transparent)]"
		></div>
	{/if}
	<div class="relative">
		{@render children?.()}
	</div>
</div>
