<script>
	import HeadLine from "$lib/Components/HeadLine/HeadLine.svelte";
import Star from "$lib/Components/Icons/Star.svelte";

   const reviews =  [
              {
                profilename: "Mariana Lopes",
                review: "Sobre o Creme Facial Revitalizante. Estou apaixonada! A textura é leve, não deixa a pele oleosa e o efeito é visível em poucos dias. Minha pele ficou mais firme e iluminada, e percebo que até a maquiagem tem durado mais. Um cuidado diário que virou meu ritual favorito!",
              },
              {
                profilename: "Camila Ferreira",
                review: "Sobre o Esfoliante Facial Antissinais. Simplesmente maravilhoso! Desde a primeira aplicação senti minha pele mais lisa e macia. O cheirinho é suave, e o produto não irrita — mesmo eu tendo pele sensível. Sinto que ele realmente renova e dá aquele glow natural que eu adoro.",
              },
              {
                profilename: "Juliana Mendes",
                review: "Sobre o Hidratante Corporal Aloecream. Esse hidratante é perfeito! A textura cremosa espalha fácil, absorve rápido e deixa a pele super hidratada o dia todo. A fragrância é delicada e relaxante, parece que acabei de sair de um spa. Já comprei o segundo frasco!",
              },
            ]
</script>

 



<section class="py-20">
	<div class="container flex flex-col">
		<div class="space-y-5 text-green-pea-950">
			<HeadLine text="Histórias de beleza e bem-estar"/>
			<p class="opacity-80"> Cada produto, um novo ritual de cuidado. Veja o que nossas clientes estão sentindo. </p>
		</div>
		<ul
			class="mt-20 flex snap-x snap-mandatory gap-4 overflow-x-auto lg:container lg:grid lg:flex-none lg:snap-none lg:grid-cols-3 lg:gap-10 lg:overflow-hidden"
		>
			{#each reviews as { review, profilename }}
				<li
					class=" bg-green-pea-900 flex w-72 shrink-0 cursor-default snap-center snap-always flex-col justify-between gap-4 rounded-md px-5 py-6 transition ease-in-out md:w-96 md:px-8 md:py-8 lg:w-full lg:snap-none"
				>
					<div class="space-y-8">
						<div class="flex flex-col gap-3 items-center">
                        <div class="flex flex-row space-x-3">
							<Star class="w-5 h-5 text-amber-400 "/>
                            <Star class="w-5 h-5 text-amber-400 "/>
                            <Star class="w-5 h-5 text-amber-400 "/>
                            <Star class="w-5 h-5 text-amber-400 "/>
                            <Star class="w-5 h-5 text-amber-400 "/>
						</div>
                        <div class="h-[2px] w-3 rounded-full bg-green-pea-50/40"></div>
                         <h4 class=" text-green-pea-50">{profilename}</h4>
                        </div>
						<div class="text-green-pea-50/80">
							<p class=" ">
								" {review} "
							</p>
						</div>
					</div>

					
				</li>
			{/each}
		</ul>
	</div>
</section>