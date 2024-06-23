<script lang="ts">
	import { List, Li, Heading } from 'flowbite-svelte';
	import { CheckCircleSolid, CloseCircleSolid, QuestionCircleSolid } from 'flowbite-svelte-icons';
	interface Component {
		checked: boolean;
		problems?: string;
	}

	interface ListType {
		[key: string]: Component;
	}
	const components: ListType = {
		accordion: {
			checked: true,
		  
		},
		alert: {
			checked: true
		},
		avatar: {
			checked: false,
			problems: 'Dropdown example not working'
		},
		badge: {
			checked: false,
			problems: 'Dismissable transition example not working'
		},
		banner: {
			checked: true
		},
		bottomNavigation: {
			checked: true
		},
		breadcrumb: {
			checked: true
		},
		buttonGroup: {
			checked: true
		},
		buttons: {
			checked: false
		},
		cards: {
			checked: false
		},
		carousel: {
			checked: false
		},
		darkmode: {
			checked: false
		},
		deviceMockups: {
			checked: false
		},
		drawer: {
			checked: false
		},
		dropdown: {
			checked: false,
			problems: 'All Dropdown not working'
		},
		footer: {
			checked: false
		},
		forms: {
			checked: false
		},
		gallery: {
			checked: false
		},
		indicators: {
			checked: false
		},
		kbd: {
			checked: false
		},
		listGroup: {
			checked: false
		},
		megaMenu: {
			checked: false
		},
		modal: {
			checked: false
		},
		navbar: {
			checked: false
		},
		pagination: {
			checked: false
		},
		popover: {
			checked: false
		},
		progress: {
			checked: false
		},
		rating: {
			checked: false
		},
		sidebar: {
			checked: false
		},
		skeleton: {
			checked: false
		},
		spinner: {
			checked: false
		},
		sppedDial: {
			checked: false
		},
		table: {
			checked: false
		},
		tabs: {
			checked: false
		},
		testdir: {
			checked: false
		},
		timeline: {
			checked: false
		},
		toast: {
			checked: false
		},
		tooltip: {
			checked: false
		},
		typography: {
			checked: false
		},
		video: {
			checked: false
		}
	};

	const forms: ListType = {
		checkbox: {
			checked: true,
			problems: 'All Checkbox not working. After the first click not working'
		},
		fileInput: {
			checked: true
		},
		floatingLabel: {
			checked: true
		},
		inputField: {
			checked: true,
			problems: 'Input Field dropdown example not working.'
		},
		radio: {
			checked: true,
			problems: 'Radio in dropdown example not working.'
		},
		range: {
			checked: false
		},
		searchInput: {
			checked: false
		},
		select: {
			checked: false
		},
		textarea: {
			checked: false
		},
		toggle: {
			checked: false
		}
	};

	const typography: ListType = {
		blockquote: {
			checked: true
		},
		heading: {
			checked: true
		},
		hr: {
			checked: true
		},
		image: {
			checked: true
		},
		link: {
			checked: true
		},
		list: {
			checked: true
		},
		paragraph: {
			checked: true,
			problems: 'Columns not working'
		},
		text: {
			checked: true
		}
	};
</script>

<h1>Flowbite Svelte Check for Svelte 5 (No Runes)</h1>

<Heading
	tag="h2"
	customSize="text-lg font-semibold"
	class="mb-2 text-lg font-semibold text-gray-900 dark:text-white">Components</Heading
>
<List tag="ul" class="space-y-1 text-gray-500 dark:text-gray-400" list="none">
	{#each Object.entries(components) as [key, { checked, problems }]}
		<Li icon>
			{#if checked && !problems}
				<CheckCircleSolid class="me-2 h-8 w-8 text-green-500 dark:text-green-400" />
			{:else if problems}
				<CloseCircleSolid class="me-2 h-8 w-8 text-red-500 dark:text-red-400" />
			{:else}
				<QuestionCircleSolid class="me-2 h-8 w-8 text-gray-500 dark:text-gray-400" />
			{/if}
			<a href="/components/{key}" class='hover:underline'>{key}</a> {#if problems} <span class="text-red-500 ml-4">({problems})</span> {/if}
		</Li>
	{/each}
</List>

<Heading
	tag="h2"
	customSize="text-lg font-semibold"
	class="mb-2 text-lg font-semibold text-gray-900 dark:text-white">Forms</Heading
>
<List tag="ul" class="space-y-1 text-gray-500 dark:text-gray-400" list="none">
	{#each Object.entries(forms) as [key, { checked, problems }]}
		<Li icon>
			{#if checked && !problems}
				<CheckCircleSolid class="me-2 h-8 w-8 text-green-500 dark:text-green-400" />
			{:else if problems}
				<CloseCircleSolid class="me-2 h-8 w-8 text-red-500 dark:text-red-400" />
			{:else}
				<QuestionCircleSolid class="me-2 h-8 w-8 text-gray-500 dark:text-gray-400" />
			{/if}
			<a href="/forms/{key}" class='hover:underline'>{key}</a> {#if problems} <span class="text-red-500 ml-4">({problems})</span> {/if}
		</Li>
	{/each}
</List>

<Heading
	tag="h2"
	customSize="text-lg font-semibold"
	class="mb-2 text-lg font-semibold text-gray-900 dark:text-white">Typography</Heading
>
<List tag="ul" class="space-y-1 text-gray-500 dark:text-gray-400" list="none">
	{#each Object.entries(typography) as [key, { checked, problems }]}
		<Li icon>
			{#if checked && !problems}
				<CheckCircleSolid class="me-2 h-8 w-8 text-green-500 dark:text-green-400" />
			{:else if problems}
				<CloseCircleSolid class="me-2 h-8 w-8 text-red-500 dark:text-red-400" />
			{:else}
				<QuestionCircleSolid class="me-2 h-8 w-8 text-gray-500 dark:text-gray-400" />
			{/if}
			<a href="/typography/{key}" class='hover:underline'>{key}</a> {#if problems} <span class="text-red-500 ml-4">({problems})</span> {/if}
		</Li>
	{/each}
</List>
