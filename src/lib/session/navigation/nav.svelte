<script>
	import { Menu } from 'lucide-svelte';
</script>

<nav class="section-spacing-padding-x">
	<div
		class="nav-bar style-nav container flex-row-reverse justify-between space-x-reverse lg:flex-row"
	>
		<div>
			<img class="h-auto w-44" src="/logo/Logo.webp" alt="" />
		</div>
		<div class="hidden flex-row space-x-10 lg:flex">
			<a class=" text-white hover:text-slate-700" href="/">Produtos</a>
			<a class=" text-white hover:text-slate-700" href="/">Informações</a>
			<a class=" text-white hover:text-slate-700" href="/">Contato</a>
		</div>
		<div class="flex lg:hidden">
			<button >
				<Menu color="#ffff" class="h-10 w-auto"></Menu>
			</button>
		</div>
	</div>
</nav>
