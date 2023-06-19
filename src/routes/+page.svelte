<script>
	import Window from '../lib/Window.svelte';
	import Highlight, { LineNumbers } from 'svelte-highlight';
	import typescript from 'svelte-highlight/languages/typescript';
	import atomOneDark from 'svelte-highlight/styles/atom-one-dark';
</script>

<svelte:head>
	{@html atomOneDark}
</svelte:head>

<div
	class="overflow-auto w-full flex-col gap-2 p-16 text-white h-full flex items-center justify-center bg-gradient-to-br from-[#1E2236] via-[#1E2236] to-[#261E36]"
>
	<Window isCode showTrafficLights icon="Typescript" windowTitle="index.ts" flexGrow>
		<Highlight
			language={typescript}
			let:highlighted
			code={`type Item = {
id: number,
name: string,
};

const items: Item[] = [
{ id: 1, name: "Item 1" },
{ id: 2, name: "Item 2" },
];

const getItemById = (id: number): Item | undefined =>
items.find((item) => item.id === id);

const getAllItems = (): Item[] => items;

const addItem = (item: Item): void => items.push(item);`}
		>
			<LineNumbers hideBorder {highlighted} />
		</Highlight>
	</Window>
	<Window showTrafficLights icon="Terminal" windowTitle="Terminal" flexGrow>
		<div>
			<span class="gap-0 flex">
				<span class="text-[#98C379]">bddy@homeserver</span>
				:
				<span class="text-[#6AB0DF]">~</span>
				$
				<span class="h-full w-[5px]" />
				<span class="text-gray-200">echo "Avery's concept design for a new code editor."</span>
			</span>
			<span class="text-gray-300">Avery's concept design for a new code editor.</span>
			<span class="gap-0 flex">
				<span class="text-[#98C379]">bddy@homeserver</span>
				:
				<span class="text-[#6AB0DF]">~</span>
				$
				<span class="ml-2 w-[2px] h-full bg-white custom-cursor-pulse" />
			</span>
		</div>
	</Window>
</div>
