<script ts="js">
	import { X } from 'lucide-svelte';
	let shown = false;
	export function show() {
		shown = true;
	}
	export function hidde() {
		shown = false;
	}
</script>

{#if shown}
	<div
		class=" absolute z-40 flex h-full w-full items-end items-center justify-center backdrop-brightness-75"
	>
		<div
			class="flex h-auto w-[90%] flex-col items-center space-y-5 rounded-lg bg-white p-8 drop-shadow-md"
		>
			<div class="flex w-full justify-end">
				<button class="close" type="button" on:click={() => hidde()}>
					<X></X>
				</button>
			</div>
			<div class="flex flex-col items-center space-y-1">
				<a class="text-black" href="/">Produtos</a>
				<a class="text-black" href="/">Contato</a>
				<a class="text-black" href="/">Informações</a>
			</div>

			<slot />
		</div>
	</div>
{/if}
