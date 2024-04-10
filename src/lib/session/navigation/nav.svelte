<script>
	import { Menu } from 'lucide-svelte';
	import Modal from '../../componentes/modal/modal.svelte';
	let modal;
</script>

<nav class="section-spacing-padding-x">
	<div
		class="nav-bar style-nav container flex-row-reverse justify-between space-x-reverse lg:flex-row"
	>
		<div>
			<img class="h-auto w-44" src="/logo/Logo.webp" alt="" />
		</div>
		<div class="hidden flex-row space-x-10 lg:flex">
			<a class=" text-white hover:text-white/80" href="/">Produtos</a>
			<a class=" text-white hover:text-white/80" href="/">Informações</a>
			<a class=" text-white hover:text-white/80" href="/">Contato</a>
		</div>
		<div class="flex lg:hidden">
			<button on:click={() => modal.show()}>
				<Menu color="#ffff" class="h-10 w-auto"></Menu>
			</button>
		</div>
	</div>
</nav>

<Modal bind:this={modal}></Modal>
