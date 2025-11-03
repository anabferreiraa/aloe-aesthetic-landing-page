<script>
	import Menu from "$lib/Components/Icons/Menu.svelte";
	import { fade } from 'svelte/transition';
	import Brand from "../Branding/Brand.svelte";

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

<nav class="container backdrop-white relative flex justify-between items-center gap-9 px-5 py-10  md:p-10">
  
  <div class="w-52 h-auto">
    <Brand class=" text-green-pea-900"/>
  </div>

  <div class="hidden lg:block">
    <ul class="flex mt-2 gap-6 ">
      {#each links as { name, href }}
        <li class="hover:underline hover:underline-offset-1">
          <a class="text-green-pea-950 hover:text-green-pea-900" href={href}>{name}</a>
        </li>
      {/each}
    </ul>
  </div>

  <div class="flex justify-center mt-2 lg:hidden">
    <button onclick={toggleMenu}>
      <Menu class="h-auto w-8 text-green-pea-800" />
    </button>
  </div>
  
</nav>

{#if menuVisible}
  <div
    transition:fade
    class="backdrop absolute left-1/2 transform -translate-x-1/2 mt-2 w-[90%] max-w-md md:max-w-xl p-8 lg:hidden text-center z-40"
  >
    <ul class="space-y-6 text-green-800">
      {#each links as { name, href }}
        <li>
          <a href={href} onclick={() => (menuVisible = false)}>
            {name}
          </a>
        </li>
      {/each}
    </ul>
  </div>
{/if}
