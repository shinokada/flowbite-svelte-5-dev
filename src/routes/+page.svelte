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
			checked: true
		},
		cards: {
			checked: false
		},
		carousel: {
			checked: false
		},
		darkmode: {
			checked: true
		},
		deviceMockups: {
			checked: true
		},
		drawer: {
			checked: false
		},
		dropdown: {
			checked: false,
			problems: 'All Dropdown not working'
		},
		footer: {
			checked: true
		},
		forms: {
			checked: false
		},
		gallery: {
			checked: true
		},
		indicators: {
			checked: true
		},
		kbd: {
			checked: true
		},
		listGroup: {
			checked: true
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
			checked: true
		},
		popover: {
			checked: false
		},
		progress: {
			checked: true
		},
		rating: {
			checked: true
		},
		sidebar: {
			checked: false
		},
		skeleton: {
			checked: true
		},
		spinner: {
			checked: true
		},
		speedDial: {
			checked: false
		},
		table: {
			checked: false
		},
		tabs: {
			checked: false
		},
		timeline: {
			checked: true
		},
		toast: {
			checked: true,
			problems: 'All transition not working'
		},
		tooltip: {
			checked: true,
			problems: 'Color dark changes to light, etc.'
		},
		typography: {
			checked: true
		},
		video: {
			checked: true
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
			checked: true
		},
		searchInput: {
			checked: true,
			problems: 'Search with dropdown example not working. Location search example not working.'
		},
		select: {
			checked: true,
		},
		textarea: {
			checked: true
		},
		toggle: {
			checked: true
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

	function analyzeComponents(components: ListType) {
		let total = 0;
		let checked = 0;
		let unchecked = 0;
		let withProblems = 0;
		let withoutProblems = 0;

		for (const component in components) {
			total++;
			checked += components[component].checked ? 1 : 0;
			unchecked += !components[component].checked ? 1 : 0;
			withProblems += components[component].problems ? 1 : 0;
		}
		withoutProblems = checked - withProblems; 

		return {
			total,
			checked,
			unchecked,
			withProblems,
			withoutProblems
		};
	}

	const componentsAnalysis = analyzeComponents(components);
	const formsAnalysis = analyzeComponents(forms);
	const typographyAnalysis = analyzeComponents(typography);

	// console.log("Components:", componentsAnalysis);
	// console.log("Forms:", formsAnalysis);
	// console.log("Typography:", typographyAnalysis);

</script>

<h1>Flowbite Svelte Check for Svelte 5 (No Runes)</h1>

<h2>Components</h2>
<List tag="ul" class="space-y-1 text-gray-500 dark:text-gray-400" list="none">
	<Li># of components - {componentsAnalysis.total}</Li>
	<Li># of checked - {componentsAnalysis.checked}</Li>
	<Li># of unchecked - {componentsAnalysis.unchecked}</Li>
	<Li liClass='text-green-500'># of without problems - {componentsAnalysis.withoutProblems}</Li>
	<Li liClass='text-red-500'># of with problems - {componentsAnalysis.withProblems}</Li>
</List>
	

<h2>Forms</h2>
<List tag="ul" class="space-y-1 text-gray-500 dark:text-gray-400" list="none">
	<Li># of components - {formsAnalysis.total}</Li>
	<Li># of checked - {formsAnalysis.checked}</Li>
	<Li># of unchecked - {formsAnalysis.unchecked}</Li>
	<Li liClass='text-green-500'># of without problems - {formsAnalysis.withoutProblems}</Li>
	<Li liClass='text-red-500'># of with problems - {formsAnalysis.withProblems}</Li>
</List>

<h2>Typography</h2>
<List tag="ul" class="space-y-1 text-gray-500 dark:text-gray-400" list="none">
	<Li># of components - {typographyAnalysis.total}</Li>
	<Li># of checked - {typographyAnalysis.checked}</Li>
	<Li># of unchecked - {typographyAnalysis.unchecked}</Li>
	<Li liClass='text-green-500'># of without problems - {typographyAnalysis.withoutProblems}</Li>
	<Li liClass='text-red-500'># of with problems - {typographyAnalysis.withProblems}</Li>
</List>

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
