<script>
	import Instagram from "$lib/Components/Icons/Instagram.svelte";
	import Whatsapp from "$lib/Components/Icons/Whatsapp.svelte";
	import { writable } from 'svelte/store';

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
						id: 'clientes',
						title: 'Cliente',
						href: '#'
					},
					{
						id: 'investidores',
						title: 'Investidores',
						href: '#'
					},
					{
						id: 'patrocinadores',
						title: 'Patrocinadores',
						href: '#'

					}
				]
			},
			{
				title: 'Ajuda e Suporte',
				links: [
					{
						id: "segurancaPrivacidade",
						title: 'Segurança e privacidade',
						href: '#'
					},
					{
						id: "TrocasDevolucoesGarantia",
						title: 'Trocas devoluções garantia',
						href: '#'
					},
					{
						id: "politicaEntrega",
						title: 'Política de entrega ',
						href: '#'
					},
					{
						id: "ContatoOuvidoria",
						title: 'Contato e Ouvidoria',
						href: '#'
					}
				]
			}
		]
	};
	const termos = [
	{
		id: 'segurancaPrivacidade',
		copywriter: {
			title: 'Termo (fictício) de Segurança e Privacidade — Aloe Aesthetic',
			description: [
				'<strong>Aviso:</strong>',
				'Aviso: este é um documento fictício e serve apenas como modelo/placeholder para fins de demonstração. Não substitui aconselhamento jurídico. Se for usar algo parecido no seu site ou app, consulte um advogado ou especialista em proteção de dados para adaptar às leis aplicáveis (por ex. LGPD — Lei Geral de Proteção de Dados no Brasil, GDPR na UE, etc.).',
				'<strong>Identificação:</strong>',
				'Responsável: Ana Beatriz Costa Ferreira',
				'Contato: whatsapp: +55 91 8495-9195',
				'E-mail: anabferreira0203@gmail.com',
			]
		}
	},
	{
		id: 'TrocasDevolucoesGarantia',
		copywriter: {
			title: 'Termo Fictício — Trocas, Devoluções e Garantia',
			description: [
                '<strong>Escopo</strong>',
				'Este termo define as regras e condições para troca, devolução e garantia dos produtos adquiridos na Aloe Aesthetic, com o objetivo de assegurar satisfação, segurança e transparência para nossos clientes.',
				'<strong>Trocas</strong>',
                'Prazo: o cliente tem até 7 dias corridos após o recebimento do produto para solicitar a troca.',
				'Condições: o produto deve estar lacrado, sem uso e com a embalagem original intacta.',
				'Procedimento: enviar mensagem via WhatsApp +55 91 8495-9195 ou e-mail anabferreira0203@gmail.com',
				'<strong>informando:</strong>',
                'Número do pedido',
                'Produto a ser trocado',
                'Motivo da troca',
                'Produtos com defeito: a Aloe Aesthetic arcará com o custo do frete de retorno e envio do novo produto.'
			]
		}
	},
	{
		id: 'politicaEntrega',
		copywriter: {
			title: 'Política Fictícia — Entrega de Produtos',
			description: [
				'<strong>Escopo</strong>',
				'Esta política define as regras e condições sobre prazo, frete e processo de entrega dos produtos adquiridos na Aloe Aesthetic, garantindo transparência e segurança aos nossos clientes.',
				'<strong>Prazo de entrega</strong>',
                'O prazo de entrega começa a contar a partir da confirmação do pagamento.',
				'O prazo estimado depende da região de entrega, tipo de frete escolhido e disponibilidade do produto.',
				'<strong>Prazo padrão:</strong>',
                'Regiões metropolitanas: 3 a 7 dias úteis',
                'Demais regiões: 7 a 15 dias úteis',
                'Observação: atrasos por motivo de força maior, feriados ou problemas com transportadoras podem ocorrer, sendo comunicados ao cliente sempre que possível.',
			]
		}
	},
	{
		id: 'ContatoOuvidoria',
		copywriter: {
			title: 'Contato e Ouvidoria — Aloe Aesthetic (modelo fictício)',
			description: [
				'<strong>Escopo</strong> ',
				'Este documento define os canais de atendimento, contato e ouvidoria da Aloe Aesthetic, garantindo que todos os clientes e usuários possam tirar dúvidas, enviar sugestões ou registrar reclamações de forma simples e segura.',
				'<strong>Canais de contato</strong>',
				'Você pode entrar em contato conosco através dos seguintes meios:',
				'WhatsApp +55 91 8495-9195',
				'<strong>Finalidades</strong>',
				'O canal de contato e ouvidoria destina-se a:',
				'Tirar dúvidas sobre produtos e serviços;',
				'Registrar sugestões e feedbacks;',
                '<strong>Prazo de resposta</strong>',
                'Todas as solicitações serão respondidas em até 3 dias úteis após o registro do contato.'
			]
		}
	},
	{
		id: 'clientes',
		copywriter: {
			title: 'Sem Clientes',
			description: [
				'Foi mal'
			],
			img:'/image/cat-with-tears-of-joy.png'
		}
	},
	{
		id: 'investidores',
		copywriter: {
			title: 'Sem investidores',
			description: [
				'Foi mal'
			],
			img:'/image/cat-with-tears-of-joy.png'
		}
	},
	{
		id: 'patrocinadores',
		copywriter: {
			title: 'Sem Patrocinadores',
			description: [
				'Foi mal'
			],
			img:'/image/cat-with-tears-of-joy.png'
		}
	}
	
	
];

	const selectedContent = writable('');
	let selectedTermos = termos;

	function openDialogFooter(content) {
		const dialog = document.getElementById('dialog');
		if (dialog instanceof HTMLDialogElement) {
			selectedContent.set(content);
			dialog.showModal();
		}
	}

	function closeDialogFooter() {
		const dialog = document.getElementById('dialog');
		if (dialog instanceof HTMLDialogElement) {
			dialog.close();
			selectedContent.set('');
		}
	}

</script>

<footer id="contato" class="relative bg-green-pea-800">
	<div class=" container py-10">
		<div class="grid grid-cols-1 lg:grid-cols-3 justify-between gap-8"> 
        <div class="flex flex-col gap-3">
			<h4 class="text-xl text-green-pea-50">{footer.text.title}</h4>
			<p class="text-green-pea-50/80 w-[280px]">{footer.text.descrition}</p>
		</div>
		
			{#each footer.infor as { title, links}}
				<ul class="flex  lg:justify-center">
				<li class="grid grid-cols-1 gap-5 justify-items-start">
					<h5 class="text-xl text-green-pea-50">{title}</h5>
					{#each links as { title, href, id }}
						<a onclick={(event) => {
						event.preventDefault();
						openDialogFooter(id);
					}} class="text-green-pea-50/80" {href}>{title}</a>
					{/each}
				</li>
			</ul>
		{/each}
		 
		<!-- Componente do diálogo -->
		<dialog id="dialog" class="overflow-y-hidden mx-auto mt-20 rounded-lg shadow-lg md:max-w-xl bg-green-pea-50  backdrop:bg-green-pea-950/60">
			{#if $selectedContent}
				{#each termos as term}
					{#if term.id === $selectedContent}
						<div class="p-6 text-center text-green-pea-950">
							<h2 class="text-2xl font-bold">{term.copywriter.title}</h2>
						</div>
						<div class="max-h-[450px] overflow-auto p-6 md:max-h-[500px]">
							<ul class="space-y-4  text-green-pea-950/80">
								{#each term.copywriter.description as desc}
									<li>{@html desc}</li>
								{/each}
								{#if term.copywriter.img}
                                    <img src={term.copywriter.img} alt="algo" width="45" height="45"/>
                                {/if}
							</ul>
						</div>
					{/if}
				{/each}
			{/if}
			<div class="flex justify-end border-t p-6 border-green-pea-900">
				<button
					class="rounded-xl bg-green-pea-400 hover:bg-green-pea-300 px-5 py-4 cursor-pointer text-green-pea-950 font-medium text-2xl"
					onclick={closeDialogFooter}>ok</button>
			</div>
		</dialog>

        </div>
	   
       <hr class="text-green-pea-50/70 mt-20" />
       <div class="grid grid-cols-1 lg:grid-cols-2 lg:justify-between gap-5 items-center mt-10">
          <img src="/logo/Logo.svg" alt="">
          <div class="flex  gap-3 lg:justify-end  ">
            <a href="https://wa.me/559184959195" target="_blank"> <Whatsapp class="w-8 h-8 text-green-pea-50"/> </a>
              <a href="https://www.instagram.com/ana_ferreirabeatriz"  target="_blank"> <Instagram class="w-8 h-8 text-green-pea-50"/> </a>
          </div>
       </div>
          
    </div>
</footer>
