<script>
	import DermatologicallyTested from "../Icons/DermatologicallyTested.svelte";
	import NotTestedOnAnimals from "../Icons/NotTestedOnAnimals.svelte";
	import Plant from "../Icons/Plant.svelte";
	import Recycle from "../Icons/Recycle.svelte";

	const productBenefits = [
		{
			icon: {
				dir: '/image/icons/',
				name: 'icon-natural-product',
				alt: 'Produto 98% natural'
			},
			title: 'Produto 98% natural.'
		},
		{
			icon: {
				dir: '/image/icons/',
				name: 'biodegradable-packaging',
				alt: 'Embalagem biodegradável'
			},
			title: 'Embalagem biodegradável'
		},
		{
			icon: {
				dir: '/image/icons/',
				name: 'icon-not-tested-on-animals',
				alt: 'Não testado em animais'
			},
			title: 'Não testado em animais'
		},
		{
			icon: {
				dir: '/image/icons/',
				name: 'icon-dermatologically-tested',
				alt: 'Dermatologicamente testado'
			},
			title: 'Dermatologicamente testado'
		}
	];
</script>

<section class="mt-20 grid grid-cols-1 items-center gap-10 md:grid-cols-3">
	<!-- Coluna esquerda -->
	<div class="flex flex-col items-center justify-center gap-20">
			<div class="flex flex-col items-center gap-2 text-center">
				<div class="relative h-20 w-20 rounded-full bg-green-50 flex justify-center items-center">
					<!-- Borda girando -->
					<div
						class="absolute inset-0 animate-spin-slow rounded-full border-1 border-dashed border-green-900/50"
					> </div>
					<!-- icone fixo -->
					<Plant class="text-green-pea-900"/>
				</div>
				<p class="text-green-pea-800">Produto 98% natural</p>
			</div>
      <div class="flex flex-col items-center gap-2 text-center">
				<div class="relative h-20 w-20 rounded-full bg-green-50 flex justify-center items-center">
					<!-- Borda girando -->
					<div
						class="absolute inset-0 animate-spin-slow rounded-full border-1 border-dashed border-green-900/50"
					> </div>
					<!-- icone fixo -->
          <Recycle class="text-green-pea-900"/>
				</div>
				<p class="text-green-pea-800">Embalagem biodegradável</p>
			</div>
	</div>

	<!-- Coluna central (imagem principal) -->
	<div class="flex justify-center">
		<img
			src="/image/products/product-benefits.webp"
			alt="Produtos Aloe Aesthetic"
			class="w-full max-w-md object-contain"
		/>
	</div>

	<!-- Coluna direita -->
	<div class="flex flex-col items-center justify-center gap-20">
		
			<div class="flex flex-col items-center gap-2 text-center">
				<div class="relative h-20 w-20 rounded-full bg-green-50 flex justify-center items-center">
					<!-- Borda girando -->
					<div
						class="absolute inset-0 animate-spin-slow rounded-full border-1 border-dashed border-green-900/50"
					> </div>
					<!-- icone fixo -->
          <NotTestedOnAnimals class="text-green-pea-900"/>
				</div>
				<p class="text-green-pea-800">Não testado em animais</p>
			</div>

      <div class="flex flex-col items-center gap-2 text-center">
				<div class="relative h-20 w-20 rounded-full bg-green-50 flex justify-center items-center">
					<!-- Borda girando -->
					<div
						class="absolute inset-0 animate-spin-slow rounded-full border-1 border-dashed border-green-900/50"
					> </div>
					<!-- icone fixo -->
          <DermatologicallyTested class="text-green-pea-900"/>
				</div>
				<p class="text-green-pea-800">Dermatologicamente testado</p>
			</div>
	
	</div>
</section>
