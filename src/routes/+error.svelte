<script lang="ts">
	import '../app.css';
	import { page } from '$app/state';
	import HouseIcon from '@lucide/svelte/icons/house';
	import FileQuestionMarkIcon from '@lucide/svelte/icons/file-question-mark';
	import LayersIcon from '@lucide/svelte/icons/layers';
	import TriangleAlertIcon from '@lucide/svelte/icons/triangle-alert';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { buttonVariants } from '$lib/components/ui/button/index.js';

	let { error }: { error: App.Error } = $props();

	const is404 = $derived(page.status === 404);
	const title = $derived(is404 ? 'Страница не найдена' : 'Что-то пошло не так');
	const description = $derived(
		is404
			? 'Такой страницы нет — возможно, она переехала, была удалена или ссылка опечатана.'
			: 'Произошла непредвиденная ошибка. Попробуйте ещё раз или вернитесь на главную.'
	);
</script>

<svelte:head>
	<title>{page.status} — {title}</title>
</svelte:head>

<div
	class="relative flex min-h-svh flex-col items-center justify-center overflow-hidden px-4 py-16 text-center"
>
	<div
		aria-hidden="true"
		class="pointer-events-none absolute inset-0 -z-10 bg-[radial-gradient(50%_40%_at_50%_0%,hsl(var(--primary)/0.12),transparent)]"
	></div>

	<Badge variant="secondary" class="gap-1.5 rounded-full px-3 py-1">
		{#if is404}
			<FileQuestionMarkIcon class="size-3.5" />
		{:else}
			<TriangleAlertIcon class="size-3.5" />
		{/if}
		Ошибка {page.status}
	</Badge>

	<h1 class="mt-6 text-7xl font-bold tracking-tight sm:text-9xl">{page.status}</h1>
	<h2 class="mt-3 text-2xl font-semibold tracking-tight">{title}</h2>
	<p class="mt-3 max-w-md text-pretty text-muted-foreground">{description}</p>

	{#if !is404 && error.message}
		<p class="mt-4 max-w-md font-mono text-xs text-muted-foreground">{error.message}</p>
	{/if}

	<div class="mt-8 flex flex-wrap items-center justify-center gap-3">
		<a href="/" class={buttonVariants({ size: 'lg' })}>
			<HouseIcon class="size-4" />
			На главную
		</a>
		<a href="/kit" class={buttonVariants({ variant: 'outline', size: 'lg' })}>
			<LayersIcon class="size-4" />
			UI Kit
		</a>
	</div>
</div>
