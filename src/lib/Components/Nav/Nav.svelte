<script>
	let links = [
		{ name: 'Produtos', href: '#home' },
		{ name: 'Informações', href: '#home' },
		{ name: 'Contato', href: '#home' }
	];
</script>

<nav class="effectglass flex justify-between p-10">
	<div> <h2>imagem</h2>
    </div>
	<ul class="flex gap-6 text-green-pea-50 hover:text-green-pea-100">
        {#each links as { name, href } }
            <li> <a href={href}>{name}</a></li>
        {/each}
	</ul>
</nav>
