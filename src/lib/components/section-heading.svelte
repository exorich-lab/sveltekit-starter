<script lang="ts">
	import type { Snippet } from 'svelte';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { cn } from '$lib/utils.js';

	let {
		eyebrow = '',
		title = '',
		description = '',
		align = 'left',
		class: className = '',
		children
	}: {
		eyebrow?: string;
		title?: string;
		description?: string;
		align?: 'left' | 'center';
		class?: string;
		children?: Snippet;
	} = $props();
</script>

<div class={cn('flex flex-col gap-3', align === 'center' && 'items-center text-center', className)}>
	{#if eyebrow}
		<Badge
			variant="secondary"
			class="gap-1.5 rounded-full px-3 py-1 text-xs font-medium tracking-wide uppercase"
		>
			{eyebrow}
		</Badge>
	{/if}
	{#if title}
		<h2 class="text-3xl font-bold tracking-tight text-balance sm:text-4xl">{title}</h2>
	{/if}
	{#if description}
		<p class="max-w-2xl text-pretty text-muted-foreground">{description}</p>
	{/if}
	{@render children?.()}
</div>
