<script lang="ts">
	import ArrowRightIcon from '@lucide/svelte/icons/arrow-right';
	import ArrowUpRightIcon from '@lucide/svelte/icons/arrow-up-right';
	import BellIcon from '@lucide/svelte/icons/bell';
	import CheckIcon from '@lucide/svelte/icons/check';
	import CopyIcon from '@lucide/svelte/icons/copy';
	import HeartIcon from '@lucide/svelte/icons/heart';
	import MailIcon from '@lucide/svelte/icons/mail';
	import PaletteIcon from '@lucide/svelte/icons/palette';
	import RocketIcon from '@lucide/svelte/icons/rocket';
	import SearchIcon from '@lucide/svelte/icons/search';
	import SettingsIcon from '@lucide/svelte/icons/settings';
	import ShieldIcon from '@lucide/svelte/icons/shield';
	import SparklesIcon from '@lucide/svelte/icons/sparkles';
	import StarIcon from '@lucide/svelte/icons/star';
	import ZapIcon from '@lucide/svelte/icons/zap';
	import { toast } from 'svelte-sonner';
	import { Button, buttonVariants } from '$lib/components/ui/button/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import {
		Card,
		CardContent,
		CardDescription,
		CardHeader,
		CardTitle
	} from '$lib/components/ui/card/index.js';
	import { Input } from '$lib/components/ui/input/index.js';
	import { Label } from '$lib/components/ui/label/index.js';
	import { Switch } from '$lib/components/ui/switch/index.js';
	import { Tabs, TabsContent, TabsList, TabsTrigger } from '$lib/components/ui/tabs/index.js';
	import { Avatar, AvatarFallback, AvatarImage } from '$lib/components/ui/avatar/index.js';
	import { Skeleton } from '$lib/components/ui/skeleton/index.js';
	import { Separator } from '$lib/components/ui/separator/index.js';
	import {
		Tooltip,
		TooltipContent,
		TooltipProvider,
		TooltipTrigger
	} from '$lib/components/ui/tooltip/index.js';
	import {
		Dialog,
		DialogContent,
		DialogDescription,
		DialogFooter,
		DialogHeader,
		DialogTitle,
		DialogTrigger
	} from '$lib/components/ui/dialog/index.js';

	let notifications = $state(true);
	let tab = $state('overview');
	let copied = $state(false);
	let email = $state('');

	function subscribe() {
		toast.success('Готово!', {
			description: email ? `Мы отправим новости на ${email}` : 'Вы подписаны на обновления'
		});
		email = '';
	}

	async function copySnippet() {
		await navigator.clipboard.writeText('pnpm create svelte@latest');
		copied = true;
		setTimeout(() => (copied = false), 1500);
	}
</script>

<!-- Hero -->
<section class="relative overflow-hidden">
	<div
		aria-hidden="true"
		class="pointer-events-none absolute inset-0 -z-10 bg-[radial-gradient(60%_50%_at_50%_0%,hsl(var(--primary)/0.12),transparent)]"
	></div>
	<div
		class="mx-auto flex w-full max-w-6xl flex-col items-center px-4 py-20 text-center sm:px-6 sm:py-28"
	>
		<Badge variant="secondary" class="gap-1.5 rounded-full px-3 py-1">
			<SparklesIcon class="size-3.5" />
			Svelte 5 · Tailwind v4 · shadcn-svelte
		</Badge>
		<h1 class="mt-6 max-w-3xl text-4xl font-bold tracking-tight text-balance sm:text-6xl">
			Стартуйте сайт или фронтенд за минуты
		</h1>
		<p class="mt-4 max-w-xl text-lg text-muted-foreground text-pretty">
			Готовый стартер: SvelteKit с runes-режимом, Tailwind CSS v4, тёмная тема и набор
			UI-компонентов — всё уже настроено и работает.
		</p>
		<div class="mt-8 flex flex-wrap items-center justify-center gap-3">
			<Button size="lg" onclick={copySnippet}>
				<CopyIcon class="size-4" />
				{copied ? 'Скопировано!' : 'Скопировать команду'}
			</Button>
			<a
				href="https://svelte.dev/docs"
				target="_blank"
				rel="noreferrer"
				class={buttonVariants({ variant: 'outline', size: 'lg' })}
			>
				Документация
				<ArrowUpRightIcon class="size-4" />
			</a>
		</div>
		<p class="mt-6 flex items-center gap-1.5 text-sm text-muted-foreground">
			<CheckIcon class="size-4 text-primary" />
			TypeScript, ESLint и Prettier из коробки
		</p>
	</div>
</section>

<!-- Features -->
<section class="mx-auto w-full max-w-6xl px-4 pb-16 sm:px-6">
	<div class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
		<Card>
			<CardHeader>
				<span
					class="flex size-10 items-center justify-center rounded-lg bg-primary/10 text-primary"
				>
					<ZapIcon class="size-5" />
				</span>
				<CardTitle>Мгновенный старт</CardTitle>
				<CardDescription>
					Один скрипт поднимает dev-сервер с HMR. Никакой лишней настройки — весь тулинг уже
					сконфигурирован.
				</CardDescription>
			</CardHeader>
		</Card>
		<Card>
			<CardHeader>
				<span
					class="flex size-10 items-center justify-center rounded-lg bg-primary/10 text-primary"
				>
					<ShieldIcon class="size-5" />
				</span>
				<CardTitle>Современный стек</CardTitle>
				<CardDescription>
					SvelteKit 2 + Svelte 5 (runes), Tailwind CSS v4 через Vite-плагин, TypeScript строгого
					режима.
				</CardDescription>
			</CardHeader>
		</Card>
		<Card>
			<CardHeader>
				<span
					class="flex size-10 items-center justify-center rounded-lg bg-primary/10 text-primary"
				>
					<PaletteIcon class="size-5" />
				</span>
				<CardTitle>Тёмная тема</CardTitle>
				<CardDescription>
					Переключатель «Светлая / Тёмная / Системная» с сохранением выбора и без вспышки при
					загрузке.
				</CardDescription>
			</CardHeader>
		</Card>
	</div>
</section>

<!-- Showcase -->
<section class="border-t bg-muted/40 py-16">
	<div class="mx-auto w-full max-w-6xl px-4 sm:px-6">
		<div class="flex items-end justify-between gap-4">
			<div>
				<h2 class="text-2xl font-semibold tracking-tight sm:text-3xl">Что уже внутри</h2>
				<p class="mt-2 text-muted-foreground">15+ shadcn-компонентов, готовых к использованию.</p>
			</div>
			<Badge variant="outline" class="hidden sm:inline-flex">components/ui</Badge>
		</div>

		<div class="mt-8 grid gap-6 lg:grid-cols-2">
			<!-- Кнопки -->
			<Card>
				<CardHeader>
					<CardTitle class="text-base">Кнопки</CardTitle>
					<CardDescription>Пять вариантов и три размера</CardDescription>
				</CardHeader>
				<CardContent class="flex flex-wrap items-center gap-3">
					<Button>Default</Button>
					<Button variant="secondary">Secondary</Button>
					<Button variant="outline">Outline</Button>
					<Button variant="ghost">Ghost</Button>
					<Button variant="destructive">Destructive</Button>
					<Button size="icon" aria-label="Поиск">
						<SearchIcon class="size-4" />
					</Button>
				</CardContent>
			</Card>

			<!-- Форма -->
			<Card>
				<CardHeader>
					<CardTitle class="text-base">Форма</CardTitle>
					<CardDescription>Input + Label + тосты через sonner</CardDescription>
				</CardHeader>
				<CardContent class="space-y-4">
					<div class="space-y-2">
						<Label for="email">Email</Label>
						<Input id="email" type="email" placeholder="you@example.com" bind:value={email} />
					</div>
					<Button class="w-full" onclick={subscribe}>
						<MailIcon class="size-4" />
						Подписаться
					</Button>
				</CardContent>
			</Card>

			<!-- Переключатели и тултипы -->
			<Card>
				<CardHeader>
					<CardTitle class="text-base">Switch и Tooltip</CardTitle>
					<CardDescription>Уведомления включены по умолчанию</CardDescription>
				</CardHeader>
				<CardContent class="space-y-4">
					<div class="flex items-center justify-between">
						<div class="flex items-center gap-2">
							<BellIcon class="size-4 text-muted-foreground" />
							<span class="text-sm">Уведомления</span>
						</div>
						<Switch bind:checked={notifications} />
					</div>
					<Separator />
					<div class="flex flex-wrap items-center gap-3">
						<TooltipProvider>
							<Tooltip>
								<TooltipTrigger>
									{#snippet child({ props })}
										<Button variant="outline" size="icon" {...props}>
											<HeartIcon class="size-4" />
										</Button>
									{/snippet}
								</TooltipTrigger>
								<TooltipContent>Добавить в избранное</TooltipContent>
							</Tooltip>
						</TooltipProvider>
						<span class="text-sm text-muted-foreground">
							Наведите на иконку — появится подсказка
						</span>
					</div>
				</CardContent>
			</Card>

			<!-- Аватар и скелетон -->
			<Card>
				<CardHeader>
					<CardTitle class="text-base">Avatar и Skeleton</CardTitle>
					<CardDescription>Загрузка профиля</CardDescription>
				</CardHeader>
				<CardContent class="space-y-4">
					<div class="flex items-center gap-3">
						<Avatar>
							<AvatarImage src="https://github.com/sveltejs.png" alt="Svelte" />
							<AvatarFallback>SV</AvatarFallback>
						</Avatar>
						<div class="space-y-2">
							<Skeleton class="h-4 w-36" />
							<Skeleton class="h-3 w-24" />
						</div>
					</div>
					<p class="text-sm text-muted-foreground">
						Svelte — компилируемый фреймворк для веб-интерфейсов.
					</p>
				</CardContent>
			</Card>

			<!-- Табы -->
			<Card>
				<CardHeader>
					<CardTitle class="text-base">Табы</CardTitle>
					<CardDescription>Навигация по разделам</CardDescription>
				</CardHeader>
				<CardContent>
					<Tabs bind:value={tab} class="w-full">
						<TabsList class="grid w-full grid-cols-3">
							<TabsTrigger value="overview">Обзор</TabsTrigger>
							<TabsTrigger value="settings">Настройки</TabsTrigger>
							<TabsTrigger value="about">О проекте</TabsTrigger>
						</TabsList>
						<TabsContent value="overview" class="mt-4 text-sm text-muted-foreground">
							Краткий обзор возможностей стартера и его структуры.
						</TabsContent>
						<TabsContent value="settings" class="mt-4 text-sm text-muted-foreground">
							Тема, язык и остальные параметры конфигурации.
						</TabsContent>
						<TabsContent value="about" class="mt-4 text-sm text-muted-foreground">
							SvelteKit · Tailwind CSS · shadcn-svelte — открытый стек.
						</TabsContent>
					</Tabs>
				</CardContent>
			</Card>

			<!-- Диалог -->
			<Card>
				<CardHeader>
					<CardTitle class="text-base">Диалог</CardTitle>
					<CardDescription>Модальное окно с фокус-менеджментом</CardDescription>
				</CardHeader>
				<CardContent>
					<Dialog>
						<DialogTrigger>
							{#snippet child({ props })}
								<Button variant="outline" {...props}>
									<SettingsIcon class="size-4" />
									Открыть настройки
								</Button>
							{/snippet}
						</DialogTrigger>
						<DialogContent class="sm:max-w-md">
							<DialogHeader>
								<DialogTitle>Настройки проекта</DialogTitle>
								<DialogDescription>
									Здесь можно изменить основные параметры. Сохранится автоматически.
								</DialogDescription>
							</DialogHeader>
							<div class="space-y-4 py-2">
								<div class="flex items-center justify-between">
									<Label for="notif-dialog" class="text-sm">Уведомления</Label>
									<Switch id="notif-dialog" bind:checked={notifications} />
								</div>
							</div>
							<DialogFooter>
								<Button type="submit">Сохранить</Button>
							</DialogFooter>
						</DialogContent>
					</Dialog>
				</CardContent>
			</Card>
		</div>
	</div>
</section>

<!-- CTA -->
<section class="mx-auto w-full max-w-6xl px-4 py-16 sm:px-6">
	<Card class="relative overflow-hidden">
		<div
			aria-hidden="true"
			class="pointer-events-none absolute inset-0 -z-10 bg-[radial-gradient(50%_60%_at_50%_100%,hsl(var(--primary)/0.12),transparent)]"
		></div>
		<CardContent class="flex flex-col items-center gap-6 py-12 text-center">
			<div class="flex items-center gap-2 text-muted-foreground">
				<StarIcon class="size-4 fill-amber-400 text-amber-400" />
				<StarIcon class="size-4 fill-amber-400 text-amber-400" />
				<StarIcon class="size-4 fill-amber-400 text-amber-400" />
				<StarIcon class="size-4 fill-amber-400 text-amber-400" />
				<StarIcon class="size-4 fill-amber-400 text-amber-400" />
			</div>
			<h2 class="max-w-xl text-2xl font-semibold tracking-tight text-balance sm:text-3xl">
				Готовы начать свой проект?
			</h2>
			<p class="max-w-md text-muted-foreground">
				Добавляйте новые shadcn-компоненты одной командой:
			</p>
			<Button
				variant="outline"
				onclick={() =>
					navigator.clipboard.writeText('pnpm dlx shadcn-svelte@latest add <component>')}
			>
				<RocketIcon class="size-4" />
				pnpm dlx shadcn-svelte@latest add button
				<ArrowRightIcon class="size-4" />
			</Button>
		</CardContent>
	</Card>
</section>
