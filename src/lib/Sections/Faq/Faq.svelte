<script>
	import CaretDown from '$lib/Components/Icons/CaretDown.svelte';
	import { onMount } from 'svelte';
	const faqs = [
		{
			question: 'Esta é uma marca real?',
			answer: {
				list: [
					'Não. Esta página foi criada apenas para fins de demonstração e portfólio. A marca Aloe Aesthetics e seus produtos são fictícios, desenvolvidos para ilustrar um projeto de design e desenvolvimento web.'
				]
			}
		},
		{
			question: 'Os produtos são indicados para todos os tipos de pele?',
			answer: {
				list: [
					'Sim! Todos os produtos da linha Aloe Aesthetics foram desenvolvidos com fórmulas suaves, testadas dermatologicamente e adequadas para todos os tipos de pele — inclusive as mais sensíveis.'
				]
			}
		},
		{
			question: 'Com que frequência devo usar o Esfoliante Facial Antissinais?',
			answer: {
				list: [
					'O ideal é utilizá-lo de 2 a 3 vezes por semana. Assim, você remove as células mortas sem agredir a pele e potencializa os efeitos do Creme Facial Revitalizante.'
				]
			}
		},
		{
			question: 'O Hidratante Corporal deixa a pele com aspecto oleoso?',
			answer: {
				list: [
					'Não! Apesar da textura cremosa, o Aloecream tem absorção rápida e proporciona uma hidratação profunda com toque seco, deixando a pele macia e confortável o dia todo.'
				]
			}
		}
	];

	onMount(() => {
		// Adicione um evento de clique no elemento summary
		document.querySelectorAll('summary').forEach((summary) => {
			summary.addEventListener('click', () => {
				// Feche todos os outros acordeões
				document.querySelectorAll('details').forEach((details) => {
					if (details !== summary.parentNode) {
						details.removeAttribute('open');
					}
				});
			});
		});
	});
</script>

<section class="py-20 mb-10">
	<div class="container text-center">
        <div class="flex flex-col">
			<div class="flex items-center justify-center flex-col gap-4">
				<div class="h-4 w-8 bg-green-pea-950"></div>
				<h3 class="text-start">Sua pele merece clareza também</h3>
			</div>
			<div class="mt-9 grid grid-cols-1 gap-3 ">
				{#each faqs as { question, answer }}
					<details
						class="group cursor-pointer space-y-2 rounded-xl border border-solid border-green-600 p-4 text-left transition-all duration-500"
					>
						<summary class="flex justify-between text-xl items-start md:text-lg ">
							<h3 class=" text-green-pea-950">{question}</h3>
							<div><CaretDown class="h-auto w-8 text-green-pea-950 group-open:rotate-180" /></div>
						</summary>
						{#each answer.list as itens}
							<p class="space-y-5 mt-5 text-green-pea-950/75">
								{@html itens}
							</p>
						{/each}
					</details>
				{/each}
			</div>
		</div>
       
	</div>
</section>

<style>
	summary::marker {
		content: '';
	}
	/* Safari */
	summary::-webkit-details-marker {
		display: none;
		color: transparent;
	}
</style>
