<script lang="ts">
	import CheckIcon from '@lucide/svelte/icons/check';
	import MonitorIcon from '@lucide/svelte/icons/monitor';
	import MoonIcon from '@lucide/svelte/icons/moon';
	import SunIcon from '@lucide/svelte/icons/sun';
	import { resetMode, setMode, userPrefersMode } from 'mode-watcher';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu/index.js';
	import { buttonVariants } from '$lib/components/ui/button/index.js';
	import { cn } from '$lib/utils.js';

	const options = [
		{ value: 'light', label: 'Светлая', icon: SunIcon },
		{ value: 'dark', label: 'Тёмная', icon: MoonIcon },
		{ value: 'system', label: 'Системная', icon: MonitorIcon }
	] as const;

	function apply(value: (typeof options)[number]['value']) {
		if (value === 'system') {
			resetMode();
		} else {
			setMode(value);
		}
	}
</script>

<DropdownMenu.Root>
	<DropdownMenu.Trigger
		class={cn(buttonVariants({ variant: 'outline', size: 'icon' }), 'relative')}
		aria-label="Переключить тему"
	>
		<SunIcon
			class="size-4 scale-100 rotate-0 transition-all duration-200 dark:scale-0 dark:-rotate-90"
		/>
		<MoonIcon
			class="absolute size-4 scale-0 rotate-90 transition-all duration-200 dark:scale-100 dark:rotate-0"
		/>
	</DropdownMenu.Trigger>
	<DropdownMenu.Content align="end" sideOffset={6}>
		{#each options as { value, label, icon: Icon } (value)}
			<DropdownMenu.Item onclick={() => apply(value)}>
				<Icon class="size-4" />
				{label}
				{#if userPrefersMode.current === value}
					<CheckIcon class="ml-auto size-4" />
				{/if}
			</DropdownMenu.Item>
		{/each}
	</DropdownMenu.Content>
</DropdownMenu.Root>
