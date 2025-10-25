<script>
	import CaretCircleDown from '$lib/Components/Icons/CaretCircleDown.svelte';
	import ShoppingCart from '$lib/Components/Icons/Shopping-cart.svelte';
	import { writable } from 'svelte/store';
	const products = [
		{
			image: {
				dir: '/image/offers/',
				name: 'hidratante-offers',
				alt: ''
			},
			text: {
				title: 'Hidratante Corporal',
				descriton:
					'Surpreenda-se com a fragrância autêntica e a textura que deixa sua pele macia, nutrida e delicadamente perfumada.'
			},
			price: {
				real_value: 170.0,
				number_installment: 2,
				installment_value: 85.66
			}
		},
		{
			image: {
				dir: '/image/offers/',
				name: 'creme-facil-offers',
				alt: ''
			},
			text: {
				title: 'Creme Facial',
				descriton:
					'O tratamento ideal para preencher, revitalizar e devolver o brilho natural da sua pele.'
			},
			price: {
				real_value: 170.0,
				number_installment: 2,
				installment_value: 85.66
			}
		},
		{
			image: {
				dir: '/image/offers/',
				name: 'esfoliante-facial-offers',
				alt: ''
			},
			text: {
				title: 'Esfoliante Facial',
				descriton:
					'Reduz a oleosidade, remove impurezas e deixa a pele macia, uniforme e renovada desde a primeira aplicação.'
			},
			price: {
				real_value: 170.0,
				number_installment: 2,
				installment_value: 85.66
			}
		}
	];

	const completeKit = {
		image: {
			dir: '/image/offers/',
			name: 'complete-kit',
			alt: ''
		},
		text: {
			title: 'Tudo para o seu bem estar e conforto',
			descriton:
				'Adquirindo a linha completa de Aloe asthetics garante uma linda nécessarie, inspirada no conforto e necessidade para o seu dia a dia'
		},
		price: {
			real_value: 442.0,
			discounted_price: 309.4,
			number_installment: 3,
			installment_value: 147.5
		}
	};

	function formatPrice(price) {
		return price.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });
	}

	let noticeVisible = false;

	//function toggleNotice() {
	//	noticeVisible = !noticeVisible;
	//}

	const dialogText = {
		title: 'Sabia que essa página é demonstrativa?',
		descriton: 'Fico muito Feliz que queira comprar, mas os produtos não existem',
		img: '/image/Winking Face.png'
	};

	const selectedContent = writable('');
	let selectedTermos = dialogText;
	function openDialog() {
		const dialog = document.getElementById('dialogOfertas');
		if (dialog instanceof HTMLDialogElement) {
			selectedContent.set(dialogText);
			dialog.showModal();
		}
	}

	function closeDialog() {
		const dialog = document.getElementById('dialogOfertas');
		if (dialog instanceof HTMLDialogElement) {
			dialog.close();
			selectedContent.set('');
		}
	}
</script>

<section id="ofertas" class=" bg-green-pea-800">
	<div
		class="relative container flex flex-col items-center justify-center bg-[url(/image/offers/background-offers-mobile.webp)] bg-cover bg-center bg-no-repeat py-20 lg:bg-[url(/image/offers/background-offers-desktop.webp)]"
	>
		<div class="grid grid-cols-1 gap-8 py-10 lg:grid-cols-3 xl:px-10">
			{#each products as { image, descriton, text, dir, alt, title, price, real_value, number_installment, installment_value }}
				<div
					class="mt-20 flex flex-col justify-between overflow-clip rounded-t-2xl rounded-br-2xl bg-green-pea-900"
				>
					<div>
						<img src="{image.dir + image.name}.webp" {alt} />
					</div>
					<div class="space-y-6 p-5 text-green-pea-50">
						<h4 class="text-2xl font-light">{text.title}</h4>
						<p class=" font-light">{text.descriton}</p>
					</div>
					<div
						class="flex flex-row justify-between bg-gradient-to-r from-green-pea-600 to-green-pea-700"
					>
						<div class="flex flex-col gap-2 p-5 text-green-pea-50">
							<span class="lg:text-lg">
								De até {price.number_installment + 'X'} de {price.installment_value.toLocaleString(
									'pt-BR',
									{
										style: 'currency',
										currency: 'BRL'
									}
								)} ou
							</span>
							<p class="text-2xl xl:text-3xl">
								{price.real_value.toLocaleString('pt-BR', {
									style: 'currency',
									currency: 'BRL'
								})} <span class="text-xl">à vista</span>
							</p>
						</div>
						<a
							href="#aviso"
							onclick={openDialog}
							class="flex cursor-pointer items-center justify-center bg-green-pea-400 p-8"
							><ShoppingCart class="h-8 w-8 text-green-pea-950" />
						</a>
					</div>
				</div>
			{/each}
		</div>

		<dialog
			id="dialogOfertas"
			class="mx-auto mt-20 overflow-y-hidden rounded-lg bg-green-pea-50 shadow-xl/30 shadow-lg"
		>
			{#if $selectedContent}
				<div
					id="aviso"
					class="flex flex-col items-center justify-between gap-4 bg-green-pea-50 p-8"
				>
					<h3 class="text-2xl text-green-pea-950">{$selectedContent.title}</h3>
					<p class="text-green-pea-950/80">{$selectedContent.descriton}</p>
					<img src={$selectedContent.img} alt="Winking Face" width="25" height="25" />
				</div>
				<div class="flex justify-end border-t border-green-pea-900 p-6">
					<button
						class="cursor-pointer rounded-xl bg-green-pea-400 px-5 py-4 text-2xl font-medium text-green-pea-950 hover:bg-green-pea-300"
						onclick={closeDialog}>ok</button
					>
				</div>
			{/if}
		</dialog>

		<div class="mt-10 flex flex-col items-center justify-center gap-6 text-center">
			<p class="text-2xl text-green-pea-50">Adquira o kit completo de Aloecram</p>
			<button class=" cursor-pointer rounded-full bg-green-pea-50">
				<a href="#kit"><CaretCircleDown class="h-10 w-10 text-green-pea-800" /></a></button
			>
		</div>
	</div>
</section>
<section id="kit" class=" bg-green-pea-900 py-20">
	<div class="container">
		<div class="grid grid-cols-1 gap-8 py-10 lg:grid-cols-2 xl:px-10">
			<div class="flex items-end justify-end">
				<img src="{completeKit.image.dir + completeKit.image.name}.webp" alt="" />
			</div>
			<div class="flex flex-col justify-between gap-5 lg:px-8">
				<h3 class="titleSection text-green-pea-50">
					{completeKit.text.title}
				</h3>
				<p class="text-2xl font-light text-green-pea-50/80">{completeKit.text.descriton}</p>
				<span class="flex flex-col gap-3 text-xl font-light text-green-pea-50/70">
					De {completeKit.price.real_value.toLocaleString('pt-BR', {
						style: 'currency',
						currency: 'BRL'
					})} por
					<p class="text-6xl font-bold text-green-pea-50">
						{completeKit.price.discounted_price.toLocaleString('pt-BR', {
							style: 'currency',
							currency: 'BRL'
						})}
					</p>
					ou {completeKit.price.number_installment + 'X'} de {completeKit.price.installment_value.toLocaleString(
						'pt-BR',
						{
							style: 'currency',
							currency: 'BRL'
						}
					)} Sem juros</span
				>
				<a
					href="#aviso"
					onclick={openDialog}
					class="cursor-pointer bg-green-pea-400 p-6 text-center text-2xl font-medium text-green-pea-950 hover:bg-green-pea-300"
					>Comprar kit Completo</a
				>
			</div>
		</div>
	</div>
</section>
