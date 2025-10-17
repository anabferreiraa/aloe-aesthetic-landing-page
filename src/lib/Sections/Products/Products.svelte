<script>
	import BoxIcons from "$lib/Components/BoxIcons/BoxIcons.svelte";

	

 const products = [
    {
        image: {
            dir:"/image/products/",
            name:"beneficios-hidratante-xl",
            alt:"",
        },
        text:{
            title:"Hidratante Corporal",
            descriton:[
                "Sinta seu corpo com a hidratação profunda de Aloecream, MARCADA PELA CREMOSIDADE E FRAGANCIA SUAVE, que se adapta ao que sua pele precisa." ,
                "é indicado para  todos os tipos de pele"
            ],
        }
    },
    {
        image: {
            dir:"/image/products/",
            name:"beneficios-esfoliante-xl",
            alt:"",
        },
        text:{
            title:"Esfoliante Facial",
            descriton:[
                "O esfoliante antissinais penetra nos poros e estimula a atividade celular, remove as células mortas da superfíce da pele." ,
                "Deixa a pele macia, luminosa e uniforme desde a primeira aplicação."
            ],
        }
    },
     {
        image: {
            dir:"/image/products/",
            name:"beneficios-creme-facial-xl",
            alt:"",
        },
        text:{
            title:"Creme Facial",
            descriton:[
                "Protege contra as agressões solares do dia a dia. Reduz rugas, recupera a firmeza e a radiância, reduz as linhas de expressões, hidrata intensamente." ,
            ],
        }
    }
 ]
</script>
<section class="py-20">
    <div class="container">
        <div class="flex items-center gap-4">
             <div class="w-4 h-4 bg-green-800"></div> <h3 class="titleCard text-green-800 ">tudo pensado para o seu bem estar!</h3>
        </div>
        <div class="mt-10 grid grid-cols-1 lg:grid-cols-3 gap-8">
            {#each products as {image, descriton, text, dir, alt, title}}
            <div class="grid grid-cols-1 justify-between border-2 border-green-pea-950 gap-6">
                <div >
                 <img  src={image.dir + image.name}.webp alt={alt}>
                </div>
                 <div class="p-5 space-y-7">
                   <h4 class="titleCard text-green-pea-950">{text.title}</h4>
                   {#each text.descriton as itens }
                     <p class="text-xl text-green-pea-800">{itens}</p>
                   {/each}
                 </div>
            </div>    
            {/each}
        </div>
        <div>
            <BoxIcons/>
        </div>
    </div>
</section>