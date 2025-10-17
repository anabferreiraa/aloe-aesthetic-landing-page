<script>
	import Facebook from "$lib/Components/Icons/Facebook.svelte";
	import Instagram from "$lib/Components/Icons/Instagram.svelte";
	import Whatsapp from "$lib/Components/Icons/Whatsapp.svelte";


	const footer = {
		text: {
			title: 'Informações da Empresa',
			descrition:
				'A empresa Aloe aesthetics foi criada figurativamente para a exposição de projeto pessoal.'
		},
		infor: [
			{
				title: 'Sobre-nós',
				links: [
					{
						title: 'Cliente',
						href: '#'
					},
					{
						title: 'Investidores',
						href: '#'
					},
					{
						title: 'Patrocinadores',
						href: '#'
					}
				]
			},
			{
				title: 'Ajuda e Suporte',
				links: [
					{
						title: 'Segurança e privacidade',
						href: '#'
					},
					{
						title: 'Trocas-devoluções-garantia',
						href: '#'
					},
					{
						title: 'Política de entrega ',
						href: '#'
					},
					{
						title: 'Contato e Ouvidoria ',
						href: '#'
					}
				]
			}
		]
	};
</script>

<footer id="contato">
	<div class="container bg-green-pea-800  p-10">
		<div class="grid grid-cols-1 lg:grid-cols-3 justify-between gap-8"> 
        <div class="flex flex-col gap-3">
			<h4 class="text-xl text-green-pea-50">{footer.text.title}</h4>
			<p class="text-green-pea-50/80 w-[280px]">{footer.text.descrition}</p>
		</div>
		{#each footer.infor as { title, links }}
			<ul>
				<li class="grid grid-cols-1 gap-5 justify-items-start">
					<h5 class="text-xl text-green-pea-50">{title}</h5>
					{#each links as { title, href }}
						<a class="text-green-pea-50/80" {href}>{title}</a>
					{/each}
				</li>
			</ul>
		{/each}
        </div>
	   
       <hr class="text-green-pea-50/70 mt-20" />
       <div class="grid grid-cols-1 lg:grid-cols-2 lg:justify-between gap-5 items-center mt-10">
          <img src="/logo/Logo.svg" alt="">
          <div class="flex  gap-3 lg:justify-end  ">
            <a href="/"> <Whatsapp class="w-8 h-8 text-green-pea-50"/> </a>
              <a href="/"> <Instagram class="w-8 h-8 text-green-pea-50"/> </a>
              <a href="/"> <Facebook class="w-8 h-8 text-green-pea-50"/> </a>
          </div>
       </div>
          
    </div>
</footer>
