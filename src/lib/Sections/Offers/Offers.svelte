<script>
	import CaretCircleDown from '$lib/Components/Icons/CaretCircleDown.svelte';
	import ShoppingCart from '$lib/Components/Icons/Shopping-cart.svelte';

	const products = [
		{
			image: {
				dir: '/image/offers/',
				name: 'hidratante-offers',
				alt: ''
			},
			text: {
				title: 'Hidratante Corporal',
				descriton: 'Surpreenda-se com a fragrância autêntica e a textura que deixa sua pele macia, nutrida e delicadamente perfumada.'
			},
            price: {
			real_value: 170.00,
			number_installment: 2,
			installment_value:85.66,
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
				descriton: 'O tratamento ideal para preencher, revitalizar e devolver o brilho natural da sua pele.'
			},
             price: {
			real_value: 170.00,
			number_installment: 2,
			installment_value:85.66,
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
				descriton: 'Reduz a oleosidade, remove impurezas e deixa a pele macia, uniforme e renovada desde a primeira aplicação.'
			},
             price: {
			real_value: 170.00,
			number_installment: 2,
			installment_value:85.66,
		}
		}
	];

	const completeKit = {
        image:{
            dir:"/image/offers/",
            name:"complete-kit",
            alt:""
        },
        text:{
          title:"Tudo para o seu bem estar e conforto",
          descriton:"Adiquirindo a linha completa de Aloe asthetics garante uma linda nécessarie, inspirada no conforto e necessidade para o seu dia a dia"
        },
         price: {
			real_value: 442.00,
            discounted_price:309.40,
			number_installment: 3,
			installment_value:147.50,
		}
    }

     function formatPrice(price) {
		return price.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });
	}
</script>

<section id="ofertas" class="mt-20">
	<div class="container flex flex-col py-20 justify-center items-center bg-[url(/image/offers/background-offers-mobile.webp)] lg:bg-[url(/image/offers/background-offers-desktop.webp)] bg-cover bg-center bg-no-repeat">
		<div
			class="grid grid-cols-1 gap-8 xl:px-10 py-10 lg:grid-cols-3"
		>
			{#each products as { image, descriton, text, dir, alt, title,price, real_value, number_installment, installment_value }}
				<div class="mt-20 flex flex-col justify-between overflow-clip rounded-t-2xl rounded-br-2xl bg-green-pea-900">
						<div>
							<img src="{image.dir + image.name}.webp" {alt} />
						</div>
						<div class="space-y-6 p-5 text-green-pea-50">
							<h4 class="text-2xl font-light">{text.title}</h4>
							<p class=" font-light">{text.descriton}</p>
						</div>
					<div class="flex flex-row justify-between bg-gradient-to-r from-green-pea-600 to-green-pea-700">
						<div class="flex flex-col gap-5 p-5 text-green-pea-50">
							<span class="lg:text-lg"> De até {price.number_installment + "X"} de {price.installment_value.toLocaleString('pt-BR', {
							style: 'currency',
							currency: 'BRL'
                    })} ou </span>
							<p class="text-2xl xl:text-3xl">{price.real_value.toLocaleString('pt-BR', {
							style: 'currency',
							currency: 'BRL'
                    })} <span class="text-xl">à vista</span></p>
						</div>
						<button class="bg-green-pea-400 p-8 cursor-pointer"><ShoppingCart class="h-8 w-8" /></button>
					</div>
				</div>
			{/each}
              
		</div>
        <div class="flex flex-col justify-center items-center gap-6 mt-10 text-center">
              <p class="text-2xl text-green-pea-50">Adquira o kit completo de Aloecram</p>
              <button class=" bg-green-pea-50 rounded-full cursor-pointer"><CaretCircleDown class="h-10 w-10 text-green-pea-800"/></button>
        </div> 
	</div>
    <div class="container bg-green-pea-900 py-20">
      <div class="xl:px-10 py-10 grid grid-cols-1 lg:grid-cols-2 gap-8">
      <div class="flex justify-end items-end">
        <img src={completeKit.image.dir + completeKit.image.name }.webp alt="">
      </div>
      <div class="flex flex-col justify-between gap-5 lg:px-8">
        <h3 class="titleSection text-green-pea-50">
            {completeKit.text.title}
        </h3>
        <p class="text-green-pea-50/80 text-2xl font-light"> {completeKit.text.descriton}</p>
        <span class="text-green-pea-50/70 text-xl font-light flex flex-col gap-3"> De {completeKit.price.real_value.toLocaleString('pt-BR', {
							style: 'currency',
							currency: 'BRL'
                    })} por <p class="text-6xl font-bold text-green-pea-50">{completeKit.price.discounted_price.toLocaleString('pt-BR', {
							style: 'currency',
							currency: 'BRL'
                    })}</p> ou {completeKit.price.number_installment + "X"} de {completeKit.price.installment_value.toLocaleString('pt-BR', {
							style: 'currency',
							currency: 'BRL'
                    })} Sem juros</span>
        <button class="bg-green-pea-400 hover:bg-green-pea-300 p-6 cursor-pointer text-green-pea-950 font-medium text-2xl">Comprar kit Completo</button>
      </div>
      
    </div>
    </div>
    
</section>
