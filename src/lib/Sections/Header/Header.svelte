<script>
	import Nav from "$lib/Components/Nav/Nav.svelte";
  const text = {
    subTitle:"Conheça a",
    title:"Aloe aesthetic",
    descrition:"Uma linha especializada em promover sua saúde e bem-estar, com fórmulas que respeitam a natureza e valorizam o equilíbrio entre você e o planeta."
  }
  const cta = {
      title:"Saiba mais",
      href:"#produtos"
  }
</script>
<header id="header" class="bg-[url(/image/header/Background-header-mobile.webp)] lg:bg-[url(/image/header/background-header-desktop.webp)] bg-center bg-no-repeat bg-cover">
<div class="container h-[980px] md:h-[1050px] lg:h-[800px] p-6">
  <Nav/>
   <div class="mt-20 lg:mt-30 text-center lg:text-start lg:space-y-8 space-y-7">
    <span class="text-green-pea-800/70">{text.subTitle}</span>
    <h1 class="text-4xl  mb-3 lg:text-7xl text-green-pea-900">{text.title}</h1>
    <p class="md:text-2xl lg:max-w-lg text-green-pea-950/80">{text.descrition}</p>
    <a href={cta.href} class="bg-green-pea-400 hover:bg-green-pea-300 mt-6 px-5 py-4 cursor-pointer text-green-pea-950 font-medium text-2xl" >{cta.title}</a>
   </div>
</div>
</header>
