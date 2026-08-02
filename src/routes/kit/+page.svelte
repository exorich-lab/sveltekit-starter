<script lang="ts">
	import { toast } from 'svelte-sonner';
	import ArrowUpRightIcon from '@lucide/svelte/icons/arrow-up-right';
	import BadgeCheckIcon from '@lucide/svelte/icons/badge-check';
	import BellIcon from '@lucide/svelte/icons/bell';
	import BoldIcon from '@lucide/svelte/icons/bold';
	import ChevronDownIcon from '@lucide/svelte/icons/chevron-down';
	import ChevronUpIcon from '@lucide/svelte/icons/chevron-up';
	import CircleCheckIcon from '@lucide/svelte/icons/circle-check';
	import CircleAlertIcon from '@lucide/svelte/icons/circle-alert';
	import CommandIcon from '@lucide/svelte/icons/command';
	import CopyIcon from '@lucide/svelte/icons/copy';
	import CrownIcon from '@lucide/svelte/icons/crown';
	import DatabaseIcon from '@lucide/svelte/icons/database';
	import DownloadIcon from '@lucide/svelte/icons/download';
	import HeartIcon from '@lucide/svelte/icons/heart';
	import HouseIcon from '@lucide/svelte/icons/house';
	import InfoIcon from '@lucide/svelte/icons/info';
	import ItalicIcon from '@lucide/svelte/icons/italic';
	import LayersIcon from '@lucide/svelte/icons/layers';
	import ListFilterIcon from '@lucide/svelte/icons/list-filter';
	import MenuIcon from '@lucide/svelte/icons/menu';
	import MousePointer2Icon from '@lucide/svelte/icons/mouse-pointer-2';
	import PaletteIcon from '@lucide/svelte/icons/palette';
	import PencilIcon from '@lucide/svelte/icons/pencil';
	import PlusIcon from '@lucide/svelte/icons/plus';
	import RocketIcon from '@lucide/svelte/icons/rocket';
	import SearchIcon from '@lucide/svelte/icons/search';
	import SendIcon from '@lucide/svelte/icons/send';
	import SettingsIcon from '@lucide/svelte/icons/settings';
	import SparklesIcon from '@lucide/svelte/icons/sparkles';
	import TextCursorIcon from '@lucide/svelte/icons/text-cursor';
	import Trash2Icon from '@lucide/svelte/icons/trash-2';
	import TriangleAlertIcon from '@lucide/svelte/icons/triangle-alert';
	import UnderlineIcon from '@lucide/svelte/icons/underline';
	import UserIcon from '@lucide/svelte/icons/user';
	import WandSparklesIcon from '@lucide/svelte/icons/wand-sparkles';
	import ZapIcon from '@lucide/svelte/icons/zap';
	import { Select as SelectPrimitive } from 'bits-ui';
	import SectionHeading from '$lib/components/section-heading.svelte';
	import GlassCard from '$lib/components/glass-card.svelte';
	import DemoCard from '$lib/components/kit/demo-card.svelte';
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
	import { Textarea } from '$lib/components/ui/textarea/index.js';
	import { Switch } from '$lib/components/ui/switch/index.js';
	import { Checkbox } from '$lib/components/ui/checkbox/index.js';
	import { RadioGroup, RadioGroupItem } from '$lib/components/ui/radio-group/index.js';
	import {
		Select,
		SelectContent,
		SelectItem,
		SelectTrigger
	} from '$lib/components/ui/select/index.js';
	import { Slider } from '$lib/components/ui/slider/index.js';
	import { Progress } from '$lib/components/ui/progress/index.js';
	import { Spinner } from '$lib/components/ui/spinner/index.js';
	import { Skeleton } from '$lib/components/ui/skeleton/index.js';
	import { Toggle } from '$lib/components/ui/toggle/index.js';
	import { ToggleGroup, ToggleGroupItem } from '$lib/components/ui/toggle-group/index.js';
	import { Kbd } from '$lib/components/ui/kbd/index.js';
	import { Tabs, TabsContent, TabsList, TabsTrigger } from '$lib/components/ui/tabs/index.js';
	import {
		Accordion,
		AccordionContent,
		AccordionItem,
		AccordionTrigger
	} from '$lib/components/ui/accordion/index.js';
	import {
		Collapsible,
		CollapsibleContent,
		CollapsibleTrigger
	} from '$lib/components/ui/collapsible/index.js';
	import { Alert, AlertDescription, AlertTitle } from '$lib/components/ui/alert/index.js';
	import {
		AlertDialog,
		AlertDialogAction,
		AlertDialogCancel,
		AlertDialogContent,
		AlertDialogDescription,
		AlertDialogFooter,
		AlertDialogHeader,
		AlertDialogTitle,
		AlertDialogTrigger
	} from '$lib/components/ui/alert-dialog/index.js';
	import { AspectRatio } from '$lib/components/ui/aspect-ratio/index.js';
	import {
		Breadcrumb,
		BreadcrumbItem,
		BreadcrumbLink,
		BreadcrumbList,
		BreadcrumbPage,
		BreadcrumbSeparator
	} from '$lib/components/ui/breadcrumb/index.js';
	import {
		CommandDialog,
		CommandEmpty,
		CommandGroup,
		CommandInput,
		CommandItem,
		CommandList,
		CommandShortcut
	} from '$lib/components/ui/command/index.js';
	import {
		DropdownMenu,
		DropdownMenuContent,
		DropdownMenuItem,
		DropdownMenuLabel,
		DropdownMenuSeparator,
		DropdownMenuTrigger
	} from '$lib/components/ui/dropdown-menu/index.js';
	import {
		Dialog,
		DialogContent,
		DialogDescription,
		DialogFooter,
		DialogHeader,
		DialogTitle,
		DialogTrigger
	} from '$lib/components/ui/dialog/index.js';
	import {
		Empty,
		EmptyContent,
		EmptyDescription,
		EmptyHeader,
		EmptyMedia,
		EmptyTitle
	} from '$lib/components/ui/empty/index.js';
	import {
		Field,
		FieldContent,
		FieldDescription,
		FieldLabel
	} from '$lib/components/ui/field/index.js';
	import {
		HoverCard,
		HoverCardContent,
		HoverCardTrigger
	} from '$lib/components/ui/hover-card/index.js';
	import {
		InputGroup,
		InputGroupInput,
		InputGroupText
	} from '$lib/components/ui/input-group/index.js';
	import {
		Menubar,
		MenubarContent,
		MenubarItem,
		MenubarMenu,
		MenubarSeparator,
		MenubarTrigger
	} from '$lib/components/ui/menubar/index.js';
	import {
		Pagination,
		PaginationContent,
		PaginationEllipsis,
		PaginationItem,
		PaginationLink,
		PaginationNext,
		PaginationPrevious
	} from '$lib/components/ui/pagination/index.js';
	import { Popover, PopoverContent, PopoverTrigger } from '$lib/components/ui/popover/index.js';
	import {
		Sheet,
		SheetContent,
		SheetDescription,
		SheetFooter,
		SheetHeader,
		SheetTitle,
		SheetTrigger
	} from '$lib/components/ui/sheet/index.js';
	import {
		Table,
		TableBody,
		TableCell,
		TableHead,
		TableHeader,
		TableRow
	} from '$lib/components/ui/table/index.js';
	import { Avatar, AvatarFallback, AvatarImage } from '$lib/components/ui/avatar/index.js';
	import {
		Tooltip,
		TooltipContent,
		TooltipProvider,
		TooltipTrigger
	} from '$lib/components/ui/tooltip/index.js';
	// form state
	let name = $state('');
	let email = $state('');
	let message = $state('');
	let search = $state('');
	let terms = $state(true);
	let notifications = $state(true);
	let radio = $state('a');
	let fruit = $state('apple');
	let volume = $state(40);
	let bold = $state(true);
	let format = $state(['bold']);
	let tab = $state('account');
	let accordion = $state('item-1');
	let pageNum = $state(1);
	let collapsibleOpen = $state(false);
	let commandOpen = $state(false);
	let sheetOpen = $state(false);
	let progress = $state(8);

	$effect(() => {
		const t = setTimeout(() => (progress = 62), 150);
		return () => clearTimeout(t);
	});

	const sections = [
		{ id: 'buttons', label: 'Кнопки', icon: MousePointer2Icon },
		{ id: 'badges', label: 'Бейджи', icon: BadgeCheckIcon },
		{ id: 'forms', label: 'Формы', icon: TextCursorIcon },
		{ id: 'feedback', label: 'Обратная связь', icon: BellIcon },
		{ id: 'data', label: 'Данные', icon: DatabaseIcon },
		{ id: 'overlays', label: 'Оверлеи', icon: LayersIcon },
		{ id: 'navigation', label: 'Навигация', icon: MenuIcon }
	];
</script>

<svelte:head>
	<title>UI Kit — SvelteKit Starter</title>
</svelte:head>

<div class="mx-auto w-full max-w-6xl px-4 py-12 sm:px-6 lg:py-16">
	<SectionHeading
		align="center"
		eyebrow="UI Kit"
		title="40 компонентов, готовых к работе"
		description="Каждый компонент можно скопировать и использовать в своём проекте. Кликайте по интерактивным демо — почти всё здесь живое."
	/>

	<div class="mt-12 grid gap-10 lg:grid-cols-[220px_1fr]">
		<!-- Sidebar -->
		<nav class="sticky top-20 hidden h-fit self-start lg:block">
			<ul class="space-y-1">
				{#each sections as { id, label, icon: Icon } (id)}
					<li>
						<a
							href="#{id}"
							class="flex items-center gap-2 rounded-lg px-3 py-2 text-sm text-muted-foreground transition-colors hover:bg-accent hover:text-accent-foreground"
						>
							<Icon class="size-4" />
							{label}
						</a>
					</li>
				{/each}
			</ul>
		</nav>

		<div class="min-w-0 space-y-16">
			<!-- Mobile chips -->
			<div class="flex gap-2 overflow-x-auto pb-1 lg:hidden">
				{#each sections as { id, label } (id)}
					<a
						href="#{id}"
						class="shrink-0 rounded-full border px-3 py-1.5 text-sm text-muted-foreground transition-colors hover:bg-accent"
					>
						{label}
					</a>
				{/each}
			</div>

			<!-- ==================== BUTTONS ==================== -->
			<section id="buttons" class="scroll-mt-24 space-y-6">
				<SectionHeading
					eyebrow="Buttons"
					title="Кнопки"
					description="Пять вариантов, три размера и состояния."
				/>
				<DemoCard
					title="Варианты"
					description="default · secondary · outline · ghost · destructive"
				>
					<Button>Default</Button>
					<Button variant="secondary">Secondary</Button>
					<Button variant="outline">Outline</Button>
					<Button variant="ghost">Ghost</Button>
					<Button variant="destructive">Destructive</Button>
				</DemoCard>
				<DemoCard title="Размеры" description="sm · default · lg · icon">
					<Button size="sm">Small</Button>
					<Button>Default</Button>
					<Button size="lg">Large</Button>
					<Button size="icon" aria-label="Поиск"><SearchIcon class="size-4" /></Button>
				</DemoCard>
				<DemoCard title="Состояния" description="disabled, loading и с иконками">
					<Button disabled>Disabled</Button>
					<Button disabled variant="outline">
						<Spinner class="size-4" />
						Загрузка...
					</Button>
					<Button>
						<RocketIcon class="size-4" />
						Запустить
					</Button>
					<Button variant="outline">
						Скачать
						<DownloadIcon class="size-4" />
					</Button>
					<a
						href="https://shadcn-svelte.com"
						target="_blank"
						rel="noreferrer"
						class={buttonVariants({ variant: 'link' })}
					>
						Ссылка-кнопка
						<ArrowUpRightIcon class="size-4" />
					</a>
				</DemoCard>
			</section>

			<!-- ==================== BADGES ==================== -->
			<section id="badges" class="scroll-mt-24 space-y-6">
				<SectionHeading eyebrow="Badges" title="Бейджи" description="Метки статусов и категорий." />
				<DemoCard title="Варианты" description="default · secondary · outline · destructive">
					<Badge>Default</Badge>
					<Badge variant="secondary">Secondary</Badge>
					<Badge variant="outline">Outline</Badge>
					<Badge variant="destructive">Destructive</Badge>
				</DemoCard>
				<DemoCard
					title="С иконками и кастомным цветом"
					description="gradient, outline с точкой, статусный"
				>
					<Badge
						class="gap-1.5 bg-gradient-to-r from-violet-500 to-fuchsia-500 text-white hover:from-violet-500 hover:to-fuchsia-500"
					>
						<SparklesIcon class="size-3.5" />
						Premium
					</Badge>
					<Badge variant="outline" class="gap-1.5">
						<span class="size-1.5 rounded-full bg-emerald-500"></span>
						Онлайн
					</Badge>
					<Badge variant="secondary" class="gap-1.5">
						<CrownIcon class="size-3.5" />
						Pro
					</Badge>
				</DemoCard>
			</section>

			<!-- ==================== FORMS ==================== -->
			<section id="forms" class="scroll-mt-24 space-y-6">
				<SectionHeading
					eyebrow="Forms"
					title="Формы"
					description="Инпуты, выбор, переключатели — всё типизировано."
				/>
				<DemoCard
					title="Input + Label"
					description="обычное поле и пароль"
					contentClass="flex-col gap-4"
				>
					<div class="grid w-full max-w-sm gap-4">
						<div class="space-y-2">
							<Label for="kit-name">Имя</Label>
							<Input id="kit-name" placeholder="Иван Петров" bind:value={name} />
						</div>
						<div class="space-y-2">
							<Label for="kit-email">Email</Label>
							<Input id="kit-email" type="email" placeholder="you@example.com" bind:value={email} />
						</div>
					</div>
				</DemoCard>
				<DemoCard
					title="InputGroup"
					description="иконка слева и кнопка справа"
					contentClass="flex-col gap-4"
				>
					<InputGroup class="w-full max-w-sm">
						<InputGroupText>
							<SearchIcon class="size-4" />
						</InputGroupText>
						<InputGroupInput placeholder="Поиск..." bind:value={search} />
					</InputGroup>
					<InputGroup class="w-full max-w-sm">
						<InputGroupInput placeholder="Сообщение..." />
						<InputGroupText>
							<Button size="sm" class="h-6 gap-1 px-2 text-xs"
								>Отправить <SendIcon class="size-3" /></Button
							>
						</InputGroupText>
					</InputGroup>
				</DemoCard>
				<DemoCard title="Textarea" description="многострочный ввод">
					<Textarea
						class="w-full max-w-sm"
						placeholder="Оставьте комментарий..."
						bind:value={message}
						rows={4}
					/>
				</DemoCard>
				<DemoCard title="Select" description="выпадающий список с поиском значений в bits-ui">
					<Select type="single" bind:value={fruit}>
						<SelectTrigger class="w-48">
							<SelectPrimitive.Value placeholder="Выберите фрукт" />
						</SelectTrigger>
						<SelectContent>
							<SelectItem value="apple">Яблоко</SelectItem>
							<SelectItem value="banana">Банан</SelectItem>
							<SelectItem value="cherry">Вишня</SelectItem>
							<SelectItem value="mango">Манго</SelectItem>
						</SelectContent>
					</Select>
				</DemoCard>
				<DemoCard title="Checkbox и RadioGroup" description="множественный и одиночный выбор">
					<div class="flex flex-col gap-4 text-left">
						<div class="flex items-center gap-2">
							<Checkbox id="kit-terms" bind:checked={terms} />
							<Label for="kit-terms">Я согласен с условиями</Label>
						</div>
						<RadioGroup bind:value={radio} class="flex flex-col gap-2">
							<div class="flex items-center gap-2">
								<RadioGroupItem value="a" id="kit-radio-a" />
								<Label for="kit-radio-a">Вариант A</Label>
							</div>
							<div class="flex items-center gap-2">
								<RadioGroupItem value="b" id="kit-radio-b" />
								<Label for="kit-radio-b">Вариант B</Label>
							</div>
						</RadioGroup>
					</div>
				</DemoCard>
				<DemoCard title="Switch и Slider" description="бинарные и числовые настройки">
					<div class="flex flex-col gap-5">
						<div class="flex items-center gap-3">
							<Switch id="kit-notif" bind:checked={notifications} />
							<Label for="kit-notif">Уведомления ({notifications ? 'вкл' : 'выкл'})</Label>
						</div>
						<div class="w-full max-w-xs space-y-2">
							<div class="flex justify-between text-sm">
								<Label>Громкость</Label>
								<span class="text-muted-foreground">{volume}%</span>
							</div>
							<Slider type="single" bind:value={volume} max={100} step={1} />
						</div>
					</div>
				</DemoCard>
				<DemoCard
					title="Toggle и ToggleGroup"
					description="одиночный и групповой переключатель форматирования"
				>
					<div class="flex flex-col gap-4">
						<div class="flex items-center gap-2">
							<Toggle bind:pressed={bold} aria-label="Жирный">
								<BoldIcon class="size-4" />
							</Toggle>
							<span class="text-sm text-muted-foreground">Текст: {bold ? 'жирный' : 'обычный'}</span
							>
						</div>
						<ToggleGroup type="multiple" bind:value={format} variant="outline">
							<ToggleGroupItem value="bold" aria-label="Жирный"
								><BoldIcon class="size-4" /></ToggleGroupItem
							>
							<ToggleGroupItem value="italic" aria-label="Курсив"
								><ItalicIcon class="size-4" /></ToggleGroupItem
							>
							<ToggleGroupItem value="underline" aria-label="Подчёркнутый"
								><UnderlineIcon class="size-4" /></ToggleGroupItem
							>
						</ToggleGroup>
					</div>
				</DemoCard>
				<DemoCard title="Field и Kbd" description="группа поля с подсказкой и клавиши-шорткаты">
					<div class="flex flex-col items-start gap-4">
						<Field class="max-w-sm">
							<FieldLabel for="kit-field">Никнейм</FieldLabel>
							<FieldContent>
								<Input id="kit-field" placeholder="@username" />
							</FieldContent>
							<FieldDescription>Будет виден в вашем профиле</FieldDescription>
						</Field>
						<div class="flex items-center gap-2">
							<span class="text-sm text-muted-foreground">Поиск:</span>
							<Kbd><CommandIcon class="size-3" /> K</Kbd>
							<Kbd>⌘</Kbd><PlusIcon class="size-3 text-muted-foreground" /><Kbd>P</Kbd>
						</div>
					</div>
				</DemoCard>
			</section>

			<!-- ==================== FEEDBACK ==================== -->
			<section id="feedback" class="scroll-mt-24 space-y-6">
				<SectionHeading
					eyebrow="Feedback"
					title="Обратная связь"
					description="Алерты, прогресс, тосты и состояния загрузки."
				/>
				<DemoCard title="Alert" description="default и destructive, с иконками">
					<div class="flex w-full max-w-md flex-col gap-3 text-left">
						<Alert>
							<InfoIcon class="size-4" />
							<AlertTitle>Информация</AlertTitle>
							<AlertDescription>Стартер обновлён до SvelteKit 2 и Tailwind v4.</AlertDescription>
						</Alert>
						<Alert variant="destructive">
							<TriangleAlertIcon class="size-4" />
							<AlertTitle>Ошибка</AlertTitle>
							<AlertDescription
								>Не удалось сохранить изменения. Попробуйте ещё раз.</AlertDescription
							>
						</Alert>
						<Alert class="border-emerald-500/40 text-emerald-700 dark:text-emerald-400">
							<CircleCheckIcon class="size-4" />
							<AlertTitle>Успех</AlertTitle>
							<AlertDescription>Изменения сохранены.</AlertDescription>
						</Alert>
					</div>
				</DemoCard>
				<DemoCard title="Progress и Spinner" description="индикаторы выполнения">
					<div class="flex w-full max-w-md flex-col gap-5">
						<div class="space-y-2">
							<div class="flex justify-between text-sm">
								<span>Загрузка данных</span>
								<span class="text-muted-foreground">{progress}%</span>
							</div>
							<Progress value={progress} />
						</div>
						<div class="flex items-center gap-3">
							<Spinner class="size-5" />
							<span class="text-sm text-muted-foreground">Обработка запроса...</span>
						</div>
					</div>
				</DemoCard>
				<DemoCard title="Skeleton" description="плейсхолдеры загрузки">
					<div class="flex w-full max-w-sm items-center gap-4">
						<Skeleton class="size-12 rounded-full" />
						<div class="space-y-2">
							<Skeleton class="h-4 w-40" />
							<Skeleton class="h-4 w-24" />
						</div>
					</div>
				</DemoCard>
				<DemoCard title="Тосты" description="svelte-sonner из коробки">
					<Button
						onclick={() => toast.success('Готово!', { description: 'Действие выполнено успешно' })}
					>
						<CircleCheckIcon class="size-4" />
						Успех
					</Button>
					<Button variant="outline" onclick={() => toast('Обычное уведомление')}>
						<BellIcon class="size-4" />
						Обычный
					</Button>
					<Button
						variant="destructive"
						onclick={() => toast.error('Ошибка', { description: 'Что-то пошло не так' })}
					>
						<CircleAlertIcon class="size-4" />
						Ошибка
					</Button>
				</DemoCard>
				<DemoCard title="Empty" description="пустое состояние">
					<Empty class="w-full max-w-sm">
						<EmptyMedia>
							<SearchIcon class="size-6 text-muted-foreground" />
						</EmptyMedia>
						<EmptyHeader>
							<EmptyTitle>Ничего не найдено</EmptyTitle>
							<EmptyDescription>Попробуйте изменить запрос или сбросить фильтры.</EmptyDescription>
						</EmptyHeader>
						<EmptyContent>
							<Button variant="outline" size="sm">
								<ListFilterIcon class="size-4" />
								Сбросить фильтры
							</Button>
						</EmptyContent>
					</Empty>
				</DemoCard>
			</section>

			<!-- ==================== DATA ==================== -->
			<section id="data" class="scroll-mt-24 space-y-6">
				<SectionHeading eyebrow="Data" title="Данные" description="Карточки, аватары, таблицы." />
				<DemoCard title="Card" description="универсальный контейнер">
					<Card class="w-full max-w-sm text-left">
						<CardHeader>
							<CardTitle>Карточка проекта</CardTitle>
							<CardDescription>Готовый блок для лендингов и дашбордов.</CardDescription>
						</CardHeader>
						<CardContent class="flex items-center gap-2 text-sm text-muted-foreground">
							<ZapIcon class="size-4 text-primary" />
							Собрано за минуту
						</CardContent>
					</Card>
				</DemoCard>
				<DemoCard title="Avatar" description="картинка с фолбэком">
					<div class="flex items-center gap-3">
						<Avatar>
							<AvatarImage src="https://github.com/sveltejs.png" alt="Svelte" />
							<AvatarFallback>SV</AvatarFallback>
						</Avatar>
						<Avatar>
							<AvatarImage src="https://github.com/huntabyte.png" alt="Huntabyte" />
							<AvatarFallback>HB</AvatarFallback>
						</Avatar>
						<Avatar>
							<AvatarFallback class="bg-primary text-primary-foreground">+9</AvatarFallback>
						</Avatar>
					</div>
				</DemoCard>
				<DemoCard title="AspectRatio" description="фиксированная пропорция блока">
					<AspectRatio
						ratio={16 / 9}
						class="w-full max-w-sm overflow-hidden rounded-lg border bg-muted"
					>
						<div
							class="grid h-full w-full place-items-center bg-gradient-to-br from-primary/15 via-background to-fuchsia-500/15 text-sm text-muted-foreground"
						>
							16:9
						</div>
					</AspectRatio>
				</DemoCard>
				<DemoCard title="Table" description="таблица данных">
					<div class="w-full max-w-md overflow-hidden rounded-lg border">
						<Table>
							<TableHeader>
								<TableRow>
									<TableHead>Проект</TableHead>
									<TableHead>Статус</TableHead>
									<TableHead class="text-right">Скорость</TableHead>
								</TableRow>
							</TableHeader>
							<TableBody>
								<TableRow>
									<TableCell class="font-medium">Starter</TableCell>
									<TableCell>
										<Badge variant="secondary" class="gap-1"
											><CircleCheckIcon class="size-3" />Готов</Badge
										>
									</TableCell>
									<TableCell class="text-right">100%</TableCell>
								</TableRow>
								<TableRow>
									<TableCell class="font-medium">Landing</TableCell>
									<TableCell>
										<Badge variant="outline">В работе</Badge>
									</TableCell>
									<TableCell class="text-right">60%</TableCell>
								</TableRow>
								<TableRow>
									<TableCell class="font-medium">API</TableCell>
									<TableCell>
										<Badge variant="destructive">Ошибка</Badge>
									</TableCell>
									<TableCell class="text-right">12%</TableCell>
								</TableRow>
							</TableBody>
						</Table>
					</div>
				</DemoCard>
			</section>

			<!-- ==================== OVERLAYS ==================== -->
			<section id="overlays" class="scroll-mt-24 space-y-6">
				<SectionHeading
					eyebrow="Overlays"
					title="Оверлеи"
					description="Диалоги, попапы, панели и палитра команд."
				/>
				<DemoCard title="Dialog" description="модальное окно">
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
								<DialogDescription>Основные параметры сохраняются автоматически.</DialogDescription>
							</DialogHeader>
							<div class="space-y-4 py-2">
								<div class="flex items-center justify-between">
									<Label for="kit-dialog-notif">Уведомления</Label>
									<Switch id="kit-dialog-notif" bind:checked={notifications} />
								</div>
							</div>
							<DialogFooter>
								<Button>Сохранить</Button>
							</DialogFooter>
						</DialogContent>
					</Dialog>
				</DemoCard>
				<DemoCard title="AlertDialog" description="подтверждение опасного действия">
					<AlertDialog>
						<AlertDialogTrigger>
							{#snippet child({ props })}
								<Button variant="destructive" {...props}>
									<Trash2Icon class="size-4" />
									Удалить проект
								</Button>
							{/snippet}
						</AlertDialogTrigger>
						<AlertDialogContent>
							<AlertDialogHeader>
								<AlertDialogTitle>Точно удалить проект?</AlertDialogTitle>
								<AlertDialogDescription>
									Это действие необратимо — все данные будут стёрты навсегда.
								</AlertDialogDescription>
							</AlertDialogHeader>
							<AlertDialogFooter>
								<AlertDialogCancel>Отмена</AlertDialogCancel>
								<AlertDialogAction>Удалить</AlertDialogAction>
							</AlertDialogFooter>
						</AlertDialogContent>
					</AlertDialog>
				</DemoCard>
				<DemoCard title="Sheet" description="выдвижная панель">
					<Sheet bind:open={sheetOpen}>
						<SheetTrigger>
							{#snippet child({ props })}
								<Button variant="outline" {...props}>
									<MenuIcon class="size-4" />
									Открыть панель
								</Button>
							{/snippet}
						</SheetTrigger>
						<SheetContent side="right">
							<SheetHeader>
								<SheetTitle>Боковая панель</SheetTitle>
								<SheetDescription>Для фильтров, корзины или меню.</SheetDescription>
							</SheetHeader>
							<div class="space-y-3 py-4">
								{#each [0, 1, 2] as i (i)}
									<div class="flex items-center gap-3 rounded-lg border p-3">
										<Skeleton class="size-9 rounded-md" />
										<div class="space-y-1.5">
											<Skeleton class="h-3.5 w-32" />
											<Skeleton class="h-3 w-20" />
										</div>
									</div>
								{/each}
							</div>
							<SheetFooter>
								<Button class="w-full">Применить</Button>
							</SheetFooter>
						</SheetContent>
					</Sheet>
				</DemoCard>
				<DemoCard title="Popover и HoverCard" description="лёгкие всплывающие блоки">
					<div class="flex flex-wrap items-center gap-4">
						<Popover>
							<PopoverTrigger>
								{#snippet child({ props })}
									<Button variant="outline" {...props}>
										<UserIcon class="size-4" />
										Профиль
									</Button>
								{/snippet}
							</PopoverTrigger>
							<PopoverContent class="w-64">
								<div class="flex items-center gap-3">
									<Avatar>
										<AvatarFallback>АП</AvatarFallback>
									</Avatar>
									<div>
										<p class="text-sm font-medium">Алексей</p>
										<p class="text-xs text-muted-foreground">alex@example.com</p>
									</div>
								</div>
								<div class="mt-3 flex gap-2">
									<Button size="sm" class="flex-1">Профиль</Button>
									<Button size="sm" variant="outline">Выйти</Button>
								</div>
							</PopoverContent>
						</Popover>
						<HoverCard>
							<HoverCardTrigger>
								{#snippet child({ props })}
									<a
										href="https://svelte.dev"
										target="_blank"
										rel="noreferrer"
										class="text-sm underline underline-offset-4"
										{...props}
									>
										@Svelte
									</a>
								{/snippet}
							</HoverCardTrigger>
							<HoverCardContent class="w-72">
								<div class="flex items-start gap-3">
									<Avatar>
										<AvatarImage src="https://github.com/sveltejs.png" alt="Svelte" />
										<AvatarFallback>SV</AvatarFallback>
									</Avatar>
									<div class="space-y-1">
										<p class="text-sm font-medium">Svelte</p>
										<p class="text-xs text-muted-foreground">Cybernetically enhanced web apps</p>
									</div>
								</div>
							</HoverCardContent>
						</HoverCard>
					</div>
				</DemoCard>
				<DemoCard title="Tooltip и DropdownMenu" description="подсказки и контекстное меню">
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
						<DropdownMenu>
							<DropdownMenuTrigger class={buttonVariants({ variant: 'outline' })}>
								<SettingsIcon class="size-4" />
								Действия
								<ChevronDownIcon class="size-4" />
							</DropdownMenuTrigger>
							<DropdownMenuContent align="end">
								<DropdownMenuLabel>Мой аккаунт</DropdownMenuLabel>
								<DropdownMenuSeparator />
								<DropdownMenuItem><UserIcon class="size-4" />Профиль</DropdownMenuItem>
								<DropdownMenuItem><PencilIcon class="size-4" />Редактировать</DropdownMenuItem>
								<DropdownMenuItem class="text-destructive focus:text-destructive">
									<Trash2Icon class="size-4" />
									Удалить
								</DropdownMenuItem>
							</DropdownMenuContent>
						</DropdownMenu>
					</div>
				</DemoCard>
				<DemoCard title="Command" description="палитра команд как в ⌘K">
					<div class="flex flex-col items-center gap-3">
						<Button
							variant="outline"
							class="w-full max-w-xs justify-between text-muted-foreground"
							onclick={() => (commandOpen = true)}
						>
							<span class="flex items-center gap-2">
								<SearchIcon class="size-4" />
								Поиск по проекту...
							</span>
							<Kbd><CommandIcon class="size-3" /> K</Kbd>
						</Button>
						<CommandDialog bind:open={commandOpen}>
							<CommandInput placeholder="Введите команду или поиск..." />
							<CommandList>
								<CommandEmpty>Ничего не найдено.</CommandEmpty>
								<CommandGroup heading="Навигация">
									<CommandItem value="home" onSelect={() => (commandOpen = false)}>
										<HouseIcon class="size-4" />
										Главная
									</CommandItem>
									<CommandItem value="kit" onSelect={() => (commandOpen = false)}>
										<LayersIcon class="size-4" />
										UI Kit
										<CommandShortcut>⌘K</CommandShortcut>
									</CommandItem>
								</CommandGroup>
								<CommandGroup heading="Действия">
									<CommandItem value="copy" onSelect={() => (commandOpen = false)}>
										<CopyIcon class="size-4" />
										Скопировать ссылку
									</CommandItem>
									<CommandItem value="theme" onSelect={() => (commandOpen = false)}>
										<PaletteIcon class="size-4" />
										Сменить тему
									</CommandItem>
								</CommandGroup>
							</CommandList>
						</CommandDialog>
					</div>
				</DemoCard>
			</section>

			<!-- ==================== NAVIGATION ==================== -->
			<section id="navigation" class="scroll-mt-24 space-y-6">
				<SectionHeading
					eyebrow="Navigation"
					title="Навигация"
					description="Табы, аккордеоны, меню и хлебные крошки."
				/>
				<DemoCard title="Tabs" description="переключение контента">
					<Tabs bind:value={tab} class="w-full max-w-md">
						<TabsList class="grid w-full grid-cols-3">
							<TabsTrigger value="account">Аккаунт</TabsTrigger>
							<TabsTrigger value="password">Пароль</TabsTrigger>
							<TabsTrigger value="notifications">Уведомления</TabsTrigger>
						</TabsList>
						<TabsContent value="account" class="mt-4 text-left text-sm text-muted-foreground">
							Настройки профиля: имя, аватар и контакты.
						</TabsContent>
						<TabsContent value="password" class="mt-4 text-left text-sm text-muted-foreground">
							Смена пароля и двухфакторная аутентификация.
						</TabsContent>
						<TabsContent value="notifications" class="mt-4 text-left text-sm text-muted-foreground">
							Email-уведомления, пуш и частота дайджестов.
						</TabsContent>
					</Tabs>
				</DemoCard>
				<DemoCard title="Accordion" description="FAQ и раскрывающиеся блоки">
					<Accordion type="single" bind:value={accordion} class="w-full max-w-md">
						<AccordionItem value="item-1">
							<AccordionTrigger>Почему Svelte?</AccordionTrigger>
							<AccordionContent class="text-left text-sm text-muted-foreground">
								Svelte компилирует компоненты в эффективный ванильный JS — без виртуального DOM.
							</AccordionContent>
						</AccordionItem>
						<AccordionItem value="item-2">
							<AccordionTrigger>Что такое Tailwind v4?</AccordionTrigger>
							<AccordionContent class="text-left text-sm text-muted-foreground">
								Новое поколение Tailwind: конфиг на CSS, быстрее сборка, больше возможностей.
							</AccordionContent>
						</AccordionItem>
						<AccordionItem value="item-3">
							<AccordionTrigger>Как добавить компонент?</AccordionTrigger>
							<AccordionContent class="text-left text-sm text-muted-foreground">
								Выполните pnpm dlx shadcn-svelte@latest add &lt;имя&gt;.
							</AccordionContent>
						</AccordionItem>
					</Accordion>
				</DemoCard>
				<DemoCard title="Collapsible" description="простой раскрывающийся блок">
					<Collapsible bind:open={collapsibleOpen} class="w-full max-w-md space-y-2">
						<div class="flex items-center justify-between rounded-lg border p-3">
							<span class="text-sm font-medium">Технологии стартера</span>
							<CollapsibleTrigger class={buttonVariants({ variant: 'ghost', size: 'icon' })}>
								{#if collapsibleOpen}
									<ChevronUpIcon class="size-4" />
								{:else}
									<ChevronDownIcon class="size-4" />
								{/if}
							</CollapsibleTrigger>
						</div>
						<CollapsibleContent class="rounded-lg border p-4 text-sm text-muted-foreground">
							SvelteKit 2 · Svelte 5 · Tailwind CSS v4 · shadcn-svelte · TypeScript
						</CollapsibleContent>
					</Collapsible>
				</DemoCard>
				<DemoCard title="Menubar" description="меню приложения">
					<Menubar class="rounded-lg border">
						<MenubarMenu>
							<MenubarTrigger>Файл</MenubarTrigger>
							<MenubarContent>
								<MenubarItem>Новый проект <Kbd>⌘N</Kbd></MenubarItem>
								<MenubarItem>Открыть... <Kbd>⌘O</Kbd></MenubarItem>
								<MenubarSeparator />
								<MenubarItem>Выход</MenubarItem>
							</MenubarContent>
						</MenubarMenu>
						<MenubarMenu>
							<MenubarTrigger>Правка</MenubarTrigger>
							<MenubarContent>
								<MenubarItem>Копировать <Kbd>⌘C</Kbd></MenubarItem>
								<MenubarItem>Вставить <Kbd>⌘V</Kbd></MenubarItem>
							</MenubarContent>
						</MenubarMenu>
						<MenubarMenu>
							<MenubarTrigger>Вид</MenubarTrigger>
							<MenubarContent>
								<MenubarItem>Тёмная тема</MenubarItem>
								<MenubarItem>Системная</MenubarItem>
							</MenubarContent>
						</MenubarMenu>
					</Menubar>
				</DemoCard>
				<DemoCard title="Breadcrumb" description="хлебные крошки">
					<Breadcrumb>
						<BreadcrumbList>
							<BreadcrumbItem>
								<BreadcrumbLink href="/">Главная</BreadcrumbLink>
							</BreadcrumbItem>
							<BreadcrumbSeparator />
							<BreadcrumbItem>
								<BreadcrumbLink href="/kit">UI Kit</BreadcrumbLink>
							</BreadcrumbItem>
							<BreadcrumbSeparator />
							<BreadcrumbItem>
								<BreadcrumbPage>Кнопки</BreadcrumbPage>
							</BreadcrumbItem>
						</BreadcrumbList>
					</Breadcrumb>
				</DemoCard>
				<DemoCard title="Pagination" description="постраничная навигация">
					<Pagination count={5} perPage={1} bind:page={pageNum}>
						<PaginationContent>
							<PaginationItem>
								<PaginationPrevious aria-label="Предыдущая" />
							</PaginationItem>
							{#each [1, 2, 3, 4, 5] as p (p)}
								<PaginationItem>
									<PaginationLink page={{ type: 'page', value: p }} isActive={pageNum === p}>
										{p}
									</PaginationLink>
								</PaginationItem>
							{/each}
							<PaginationItem>
								<PaginationEllipsis />
							</PaginationItem>
							<PaginationItem>
								<PaginationNext aria-label="Следующая" />
							</PaginationItem>
						</PaginationContent>
					</Pagination>
				</DemoCard>
			</section>

			<!-- Footer CTA -->
			<GlassCard glow class="p-8 text-center">
				<div class="flex flex-col items-center gap-4">
					<Badge variant="outline" class="gap-1.5 rounded-full px-3 py-1">
						<WandSparklesIcon class="size-3.5" />
						Компоненты копируются в src/lib/components/ui
					</Badge>
					<p class="max-w-lg text-pretty text-sm text-muted-foreground">
						Нужен компонент, которого нет в наборе? Он добавляется одной командой — всё остальное
						стартер уже настроил.
					</p>
					<Button
						onclick={() =>
							navigator.clipboard.writeText('pnpm dlx shadcn-svelte@latest add <component>')}
					>
						<CopyIcon class="size-4" />
						Скопировать команду
					</Button>
				</div>
			</GlassCard>
		</div>
	</div>
</div>
