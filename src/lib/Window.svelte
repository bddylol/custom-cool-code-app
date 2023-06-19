<script lang="ts">
	import type { Icon } from './types';

	export let showTrafficLights: boolean = true;
	export let icon: Icon | null = null;
	export let flexGrow: boolean = false;
	export let windowTitle: string = 'Window Title';
	export let isCode: boolean = false;
</script>

<div
	class={`flex flex-col bg-[rgba(0,0,0,0.07)] border border-[rgba(0,0,0,0.25)] rounded-md min-w-[170px] ${
		flexGrow && 'w-full'
	}`}
>
	<div class="flex bg-[rgba(0,0,0,0.09)] p-2 gap-4 items-center flex-row">
		{#if showTrafficLights}
			<div class="flex flex-row gap-2 items-center w-full">
				<div class="w-[16px] h-[16px] rounded-full bg-[#DC4D47]" />
				<div class="w-[16px] h-[16px] rounded-full bg-[#DBA42C]" />
				<div class="w-[16px] h-[16px] rounded-full bg-[#22AA39]" />
			</div>
		{/if}
		<div class="flex flex-row gap-2 items-center">
			{#if icon == 'Typescript'}
				<svg
					width="16"
					height="16"
					viewBox="0 0 15 15"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
				>
					<g clip-path="url(#clip0_1_16)">
						<path d="M0.5 7.5V0.5H14.5V14.5H0.5" fill="#007ACC" />
						<path
							d="M3.5695 7.5245V8.095H5.3895V13.275H6.681V8.095H8.501V7.535C8.501 7.22 8.501 6.9645 8.487 6.9575C8.487 6.947 7.3775 6.9435 6.03 6.9435L3.58 6.954V7.528L3.5695 7.5245ZM11.749 6.94C12.106 7.024 12.379 7.185 12.624 7.4405C12.7535 7.5805 12.946 7.8255 12.96 7.8885C12.96 7.9095 12.3545 8.319 11.987 8.5465C11.973 8.557 11.917 8.4975 11.861 8.4065C11.679 8.1475 11.4935 8.0355 11.203 8.0145C10.783 7.9865 10.503 8.207 10.503 8.5745C10.503 8.6865 10.524 8.7495 10.566 8.8405C10.6605 9.033 10.8355 9.1485 11.378 9.3865C12.379 9.817 12.813 10.1005 13.0755 10.5065C13.373 10.9615 13.4395 11.6755 13.24 12.211C13.016 12.7955 12.47 13.191 11.6895 13.3205C11.4445 13.3625 10.8845 13.3555 10.622 13.31C10.062 13.205 9.5265 12.925 9.1975 12.5645C9.068 12.4245 8.8195 12.05 8.8335 12.0255L8.9665 11.9415L9.4915 11.637L9.887 11.406L9.978 11.5285C10.0935 11.7105 10.3525 11.9555 10.503 12.0395C10.958 12.274 11.567 12.2425 11.868 11.9695C11.9975 11.8505 12.0535 11.7245 12.0535 11.5495C12.0535 11.3885 12.029 11.315 11.9485 11.1925C11.8365 11.0385 11.6125 10.9125 10.9825 10.6325C10.258 10.3245 9.95 10.1285 9.663 9.8275C9.4985 9.6455 9.348 9.362 9.278 9.1275C9.2255 8.9245 9.208 8.4275 9.257 8.228C9.4075 7.528 9.936 7.038 10.692 6.898C10.937 6.849 11.5145 6.87 11.756 6.933L11.749 6.94Z"
							fill="white"
						/>
					</g>
					<defs>
						<clipPath id="clip0_1_16">
							<rect x="0.5" y="0.5" width="14" height="14" rx="2" fill="white" />
						</clipPath>
					</defs>
				</svg>
			{/if}
			{#if icon == 'Terminal'}
				<svg
					width="16"
					height="16"
					viewBox="0 0 14 15"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M2.91667 4.58334L5.83334 7.5L2.91667 10.4167M7.00001 11.5833H11.0833"
						stroke="white"
						stroke-linecap="round"
						stroke-linejoin="round"
					/>
				</svg>
			{/if}
			<span>{windowTitle}</span>
		</div>
		<div class="flex flex-row h-full w-full" />
	</div>
	<div class={`flex w-full h-full ${!isCode && 'p-4'}`}>
		<slot />
	</div>
</div>
