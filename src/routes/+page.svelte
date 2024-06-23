<script>
	import { List, Li, Heading } from 'flowbite-svelte';
	import { CheckCircleSolid, CloseCircleSolid } from 'flowbite-svelte-icons';
	const components = {
		accordion: true,
		alert: true,
		avatar: false,
		badge: false,
		banner: true,
		bottomNavigation: true,
		breadcrumb: true,
		buttonGroup: true,
		buttons: false,
		cards: false,
		carousel: false,
		darkmode: false,
		deviceMockups: false,
		drawer: false,
		dropdown: false,
		footer: false,
		forms: false,
		gallery: false,
		indicators: false,
		kbd: false,
		listGroup: false,
		megaMenu: false,
		modal: false,
		navbar: false,
		pagination: false,
		popover: false,
		progress: false,
		rating: false,
		sidebar: false,
		skeleton: false,
		spinner: false,
		sppedDial: false,
		table: false,
		tabs: false,
		testdir: false,
		timeline: false,
		toast: false,
		tooltip: false,
		typography: false,
		video: false
	};

	const forms = {
		checkbox: false,
		fileInput: false,
		floatingLabel: false,
		inputField: false,
		radio: false,
		range: false,
		searchInput: false,
		select: false,
		textarea: false,
		toggle: false
	};

	const typography = {
		blockquote: true,
		heading: true,
		hr: true,
		image: true,
		link: false,
		list: false,
		paragraph: false,
		text: false
	};
</script>

<h1>Flowbite Svelte Check for Svelte 5 (No Runes)</h1>

<Heading
	tag="h2"
	customSize="text-lg font-semibold"
	class="mb-2 text-lg font-semibold text-gray-900 dark:text-white">Components</Heading
>
<List tag="ul" class="space-y-1 text-gray-500 dark:text-gray-400" list="none">
	{#each Object.entries(components) as [key, value]}
		<Li icon>
			{#if value}
				<CheckCircleSolid class="me-2 h-5 w-5 text-green-500 dark:text-green-400" />
			{:else}
				<CloseCircleSolid class="me-2 h-5 w-5 text-gray-500 dark:text-gray-400" />
			{/if}
			<a href="/components/{key}">{key}</a>
		</Li>
	{/each}
</List>

<Heading
	tag="h2"
	customSize="text-lg font-semibold"
	class="mb-2 text-lg font-semibold text-gray-900 dark:text-white">Forms</Heading
>
<List tag="ul" class="space-y-1 text-gray-500 dark:text-gray-400" list="none">
	{#each Object.entries(forms) as [key, value]}
		<Li icon>
			{#if value}
				<CheckCircleSolid class="me-2 h-5 w-5 text-green-500 dark:text-green-400" />
			{:else}
				<CloseCircleSolid class="me-2 h-5 w-5 text-gray-500 dark:text-gray-400" />
			{/if}
			<a href="/forms/{key}">{key}</a>
		</Li>
	{/each}
</List>

<Heading
	tag="h2"
	customSize="text-lg font-semibold"
	class="mb-2 text-lg font-semibold text-gray-900 dark:text-white">Typography</Heading
>
<List tag="ul" class="space-y-1 text-gray-500 dark:text-gray-400" list="none">
	{#each Object.entries(typography) as [key, value]}
		<Li icon>
			{#if value}
				<CheckCircleSolid class="me-2 h-5 w-5 text-green-500 dark:text-green-400" />
			{:else}
				<CloseCircleSolid class="me-2 h-5 w-5 text-gray-500 dark:text-gray-400" />
			{/if}
			<a href="/typography/{key}">{key}</a>
		</Li>
	{/each}
</List>
