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
		class="absolute bottom-0 z-40 flex h-full w-full items-end justify-center backdrop-brightness-75"
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
				<a href="/">Produtos</a>
				<a href="/">Contato</a>
				<a href="/">Informações</a>
			</div>

			<slot />
		</div>
	</div>
{/if}
