<script>
	import Menu from "$lib/Components/Icons/Menu.svelte";
	import { fade } from 'svelte/transition';

	let links = [
		{ name: 'Produtos', href: '#produtos' },
		{ name: 'Informações', href: '#sobre' },
		{ name: 'Contato', href: '#contato' }


	];

	let menuVisible = false;

	function toggleMenu() {
		menuVisible = !menuVisible;
	}

</script>

<nav class="effectglassNav backdrop-blur-md relative flex justify-between gap-5 p-10">
  <div class="w-52 h-auto">
    <img src="/logo/Logo-green.svg" alt="">
  </div>

  <div class="hidden lg:block">
    <ul class="flex mt-2 gap-6 text-green-pea-800 hover:text-green-pea-900">
      {#each links as { name, href }}
        <li class="hover:underline hover:underline-offset-1">
          <a href={href}>{name}</a>
        </li>
      {/each}
    </ul>
  </div>

  <div class="flex justify-center lg:hidden">
    <button on:click={toggleMenu}>
      <Menu class="h-auto w-8 text-green-pea-800" />
    </button>
  </div>
</nav>

{#if menuVisible}
  <div
    transition:fade
    class="effectglassNav backdrop-blur-md absolute left-1/2 transform -translate-x-1/2 mt-2 w-[90%] max-w-md md:max-w-xl p-8 lg:hidden text-center z-40"
  >
    <ul class="space-y-6 text-green-800">
      {#each links as { name, href }}
        <li>
          <a href={href} on:click={() => (menuVisible = false)}>
            {name}
          </a>
        </li>
      {/each}
    </ul>
  </div>
{/if}
