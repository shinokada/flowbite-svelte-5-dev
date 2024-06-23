<script>
  import { Button, Dropdown, DropdownItem } from 'flowbite-svelte';
  import { ChevronDownOutline } from 'flowbite-svelte-icons'; 
  import { page } from '$app/stores';
  $: activeUrl = $page.url.pathname;
</script>

<h1>Dropdown NOT WORKING</h1>
<h2>Example</h2>
<div class='flex'>
<Button>Dropdown button<ChevronDownOutline class="w-6 h-6 ms-2 text-white dark:text-white" /></Button>
<Dropdown>
  <DropdownItem>Dashboard</DropdownItem>
  <DropdownItem>Settings</DropdownItem>
  <DropdownItem>Earnings</DropdownItem>
  <DropdownItem>Sign out</DropdownItem>
</Dropdown>
</div>

<h2>Adding links and active class</h2>
<div class='flex'>
  <Button>Dropdown button<ChevronDownOutline class="w-6 h-6 ms-2 text-white dark:text-white" /></Button>
<Dropdown {activeUrl}>
  <DropdownItem href="/">Home</DropdownItem>
  <DropdownItem href="/dropdown">Dropdown</DropdownItem>
  <DropdownItem href="/docs/components/accordion">Accordion</DropdownItem>
  <DropdownItem href="/docs/components/alert">Alert</DropdownItem>
</Dropdown>
</div>