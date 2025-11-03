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
  const idSection = "header"
</script>
<header id={idSection} class="bg-[url(/image/header/background-mobile.webp)] lg:bg-[url(/image/header/background-header-desktop.webp)] bg-center bg-no-repeat bg-cover pt-3 h-[980px] md:h-[1050px] lg:h-[790px]">
<Nav />
<div class="container grid grid-cols-1 lg:grid-cols-2  mt-15 lg:mt-0 lg:items-center h-[85%]">
<div class="flex flex-col gap-5 text-center lg:text-start text-green-pea-950">
    <h2 class="">{text.subTitle}</h2>
    <h1 class="text-4xl lg:text-7xl">{text.title}</h1>
    <p class="md:text-2xl opacity-70">{text.descrition}</p>
    
    <div>
      <button class="bg-green-pea-600 hover:bg-green-pea-400 px-6 py-4 text-green-pea-50 text-2xl"><a href={cta.href}  >{cta.title} </a></button>
    </div>
      
       
   </div>
   
</div>
  
</header>
  