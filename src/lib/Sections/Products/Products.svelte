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
                "Descubra o toque da hidratação profunda com textura cremosa e fragrância suave." ,
                "Aloecream se adapta ao que sua pele precisa, proporcionando nutrição intensa e conforto duradouro.",
                "Indicado para todos os tipos de pele."
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
            title:"Esfoliante Facial Antissinais",
            descriton:[
                "Renove sua pele desde a primeira aplicação." ,
                "O Esfoliante Facial Antissinais remove as células mortas, estimula a renovação celular e revela uma pele mais macia, luminosa e uniforme.",
                "Indicado para todos os tipos de pele."
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
            title:"Creme Facial Revitalizante",
            descriton:[
                "Proteja e realce a beleza natural do seu rosto." ,
                "O Creme Facial Revitalizante hidrata profundamente, reduz rugas e linhas de expressão e recupera a firmeza e o brilho da pele.",
                "Perfeito para o cuidado diário e a defesa contra as agressões externas."
            ],
        }
    }
 ]
</script>
<section id="produtos" class="py-20">
    <div class="container">
        <div class="flex items-center gap-4">
             <div class="w-4 h-4 bg-green-pea-950"></div> <h3 class="titleCard text-green-pea-950 ">Tudo pensado para o seu bem estar!</h3>
        </div>
        <div class="mt-10 grid grid-cols-1 lg:grid-cols-3 gap-6">
            {#each products as {image, descriton, text, dir, alt, title}}
            <div class="grid grid-cols-1 justify-between border-1 border-green-pea-950 gap-4">
                <div>
                 <img  src={image.dir + image.name}.webp alt={alt}>
                </div>
                 <div class="p-5 space-y-4 text-green-pea-950">
                   <h4 class="text-2xl  font-bold">{text.title}</h4>
                   {#each text.descriton as itens }
                     <p class="text-xl  opacity-70">{itens}</p>
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