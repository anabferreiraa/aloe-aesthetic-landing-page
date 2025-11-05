<script>
	import Menu from '$lib/Components/Icons/Menu.svelte';
	import { fade } from 'svelte/transition';
	import Brand from '../Branding/Brand.svelte';

	let links = [
		{ name: 'Informações', href: '#sobre' },
		{ name: 'Produtos', href: '#produtos' },
		{ name: 'Ofertas', href: '#ofertas' },
		{ name: 'Kit', href: '#kit' }
	];

	let menuVisible = false;

	function toggleMenu() {
		menuVisible = !menuVisible;
	}
</script>

<div class="relative container">
	<nav
		class="backdrop-white container flex items-center justify-between gap-9 px-5 py-5 lg:py-10"
	>
		<div class="h-auto w-52">
			<Brand class="w-42 text-green-pea-900" />
		</div>

		<div class="hidden lg:block">
			<ul class="mt-2 flex gap-6">
				{#each links as { name, href }}
					<li class="hover:underline hover:underline-offset-1">
						<a class="text-green-pea-950 hover:text-green-pea-900" {href}>{name}</a>
					</li>
				{/each}
			</ul>
		</div>

		<div class="flex justify-center lg:hidden">
			<button onclick={toggleMenu}>
				<Menu class="h-auto w-7 text-green-pea-800" />
			</button>
		</div>
	</nav>
	{#if menuVisible}
  <div class="container absolute z-40 right-0 mt-2 ">
    <div
			transition:fade
			class="backdrop-white p-8 text-center lg:hidden"
		>
			<ul class="space-y-6 text-green-800">
				{#each links as { name, href }}
					<li>
						<a {href} onclick={() => (menuVisible = false)}>
							{name}
						</a>
					</li>
				{/each}
			</ul>
		</div>
  </div>
		
	{/if}
</div>
