<script>
  import { Heading, P, List, Li, Label, MultiSelect, Button, Datepicker, Dropdown, DropdownItem } from 'flowbite-svelte';
	import { ChevronDownOutline } from 'flowbite-svelte-icons';

  
	const rowClass = 'border-b-2 border-gray-300 flex items-center p-4 whitespace-nowrap';
	const cellClass = 'inline-flex basis-10/12';
	const headerCellClass = `inline-flex basis-2/12 font-bold w-28 mr-2`;
	const buttonClass = 'mx-2';
	const today = new Date();
	let dateRange = { from: today, to: today };
</script>

<div class='p-9'>
<Heading tag="h1">Flowbite-Svelte Playground</Heading>
<List tag="ol">
  <Li class="text-2xl">Fork this Stackblitz project</Li>
  <Li class="text-2xl">Update Flowbite-Svelte by running `pnpm i -D flowbite-svelte@latest`</Li>
  <Li class="text-2xl">Run `pnpm update` to update dependencies.</Li>
  <Li class="text-2xl">Add your code</Li>
</List>

</div>

<div class={rowClass}>
	<div class={headerCellClass}>Date:</div>
	<div class={cellClass}>
		<Button
			class="bg-transparent py-0 text-center text-sm font-medium text-gray-500 hover:bg-transparent hover:text-gray-900 focus:ring-transparent dark:bg-transparent dark:text-gray-400 dark:hover:bg-transparent dark:hover:text-white dark:focus:ring-transparent"
			>Today<ChevronDownOutline class="m-2.5 ms-1.5 w-2.5" /></Button
		>
		<Dropdown class="w-40">
			<DropdownItem>Yesterday</DropdownItem>
			<DropdownItem>Today</DropdownItem>
			<DropdownItem>Last 7 days</DropdownItem>
			<DropdownItem>Last 30 days</DropdownItem>
			<DropdownItem>Last 90 days</DropdownItem>
		</Dropdown>
		<div class="basis-10/12">
			<Datepicker
				color="purple"
				range
				required={true}
				bind:rangeFrom={dateRange.from}
				bind:rangeTo={dateRange.to}
			/>
		</div>
	</div>
</div>