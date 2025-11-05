<script>
	import Nav from '$lib/Components/Nav/Nav.svelte';
	const text = {
		subTitle: 'Conheça a',
		title: 'Aloe aesthetic',
		descrition:
			'Uma linha especializada em promover sua saúde e bem-estar, com fórmulas que respeitam a natureza e valorizam o equilíbrio entre você e o planeta.'
	};
	const cta = {
		title: 'Saiba mais',
		href: '#produtos'
	};
	const idSection = 'header';
</script>

<header
	id={idSection}
	class="h-[980px] bg-[url(/image/header/background-mobile.webp)] bg-cover bg-center bg-no-repeat pt-3 md:h-[1050px] lg:h-[790px] lg:bg-[url(/image/header/background-header-desktop.webp)]"
>
	<Nav />
	<div class="container mt-15 grid h-[85%] grid-cols-1 lg:mt-0 lg:grid-cols-2 lg:items-center">
		<div class="flex flex-col gap-5 text-center text-green-pea-950 lg:text-start">
			<h2>{text.subTitle}</h2>
			<h1 >{text.title}</h1>
			<p>{text.descrition}</p>
			<div class="flex">
					<a class="bg-green-pea-600 px-6 py-4 text-xl text-green-pea-50 rounded-xl hover:bg-green-pea-400" href={cta.href}> {cta.title}</a>
			</div>
		</div>
	</div>
</header>
