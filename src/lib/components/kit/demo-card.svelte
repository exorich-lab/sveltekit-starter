<script lang="ts">
	import type { Snippet } from 'svelte';
	import { cn } from '$lib/utils.js';

	let {
		title = '',
		description = '',
		class: className = '',
		contentClass = '',
		children
	}: {
		title?: string;
		description?: string;
		class?: string;
		/** Extra classes for the preview area (e.g. to stretch children) */
		contentClass?: string;
		children?: Snippet;
	} = $props();
</script>

<div class={cn('overflow-hidden rounded-xl border bg-card shadow-sm', className)}>
	<div
		class={cn(
			'flex min-h-24 flex-wrap items-center justify-center gap-3 border-b bg-muted/40 p-6',
			contentClass
		)}
	>
		{@render children?.()}
	</div>
	{#if title}
		<div class="px-5 py-3">
			<p class="text-sm font-medium">{title}</p>
			{#if description}
				<p class="mt-0.5 text-xs text-muted-foreground">{description}</p>
			{/if}
		</div>
	{/if}
</div>
