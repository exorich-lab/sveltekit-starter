<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
	import { ModeWatcher } from 'mode-watcher';
	import ThemeToggle from '$lib/components/theme-toggle.svelte';
	import { Toaster } from '$lib/components/ui/sonner/index.js';
	import { buttonVariants } from '$lib/components/ui/button/index.js';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>SvelteKit Starter</title>
</svelte:head>

<ModeWatcher />

<div class="relative flex min-h-svh flex-col">
	<header class="sticky top-0 z-40 w-full border-b bg-background/80 backdrop-blur">
		<div class="mx-auto flex h-14 w-full max-w-6xl items-center gap-4 px-4 sm:px-6">
			<a href="/" class="flex items-center gap-2 font-semibold tracking-tight">
				<span
					class="flex size-6 items-center justify-center rounded-md bg-primary text-xs font-bold text-primary-foreground"
				>
					S
				</span>
				<span class="hidden sm:inline">SvelteKit Starter</span>
			</a>
			<nav class="hidden items-center gap-1 md:flex">
				<a href="/" class={buttonVariants({ variant: 'ghost', size: 'sm' })}>Главная</a>
				<a href="/kit" class={buttonVariants({ variant: 'ghost', size: 'sm' })}>UI Kit</a>
				<a
					href="https://svelte.dev/docs"
					target="_blank"
					rel="noreferrer"
					class={buttonVariants({ variant: 'ghost', size: 'sm' })}
				>
					Документация
				</a>
			</nav>
			<div class="ml-auto">
				<ThemeToggle />
			</div>
		</div>
	</header>

	<main class="flex-1">
		{@render children()}
	</main>

	<footer class="border-t py-6">
		<p class="text-center text-sm text-muted-foreground">
			Сделано на Svelte 5 · SvelteKit · Tailwind CSS v4
		</p>
	</footer>
</div>

<Toaster richColors />
