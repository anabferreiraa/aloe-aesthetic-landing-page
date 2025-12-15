<script>
	import BoxIcons from "$lib/Components/BoxIcons/BoxIcons.svelte";
	import HeadLine from "$lib/Components/HeadLine/HeadLine.svelte";
    
 const idSection = "produtos"

 const products = [
    {
        image: {
            name:"body-cream-benefit",
            alt:"",
        },
        title:"Hidratante Corporal",
        description:[
                "Descubra o toque da hidratação profunda com textura cremosa e fragrância suave." ,
                "Aloecream se adapta ao que sua pele precisa, proporcionando nutrição intensa e conforto duradouro.",
                "Indicado para todos os tipos de pele.",
                
            ],
        specification: [
                "Contém: 500ml"
        ]
    },
    {
        image: {
            name:"facial-exfoliator-benefit",
            alt:"",
        },
            title:"Esfoliante Facial Antissinais",
            description:[
                "Renove sua pele desde a primeira aplicação." ,
                "O Esfoliante Facial Antissinais remove as células mortas, estimula a renovação celular e revela uma pele mais macia, luminosa e uniforme.",
                "Indicado para todos os tipos de pele.",
               
            ],
            specification: [
                "Contém: 250ml"
        ]
    },
     {
        image: {
            name:"facial-cream-benefit",
            alt:"",
        },
            title:"Creme Facial Revitalizante",
            description:[
                "Proteja e realce a beleza natural do seu rosto." ,
                "O Creme Facial Revitalizante hidrata profundamente, reduz rugas e linhas de expressão e recupera a firmeza e o brilho da pele.",
                "Perfeito para o cuidado diário e a defesa contra as agressões externas.",
               
            ],
              specification: [
               "Contém: 40ml"
        ]
        
    }
 ]
</script>
<section id={idSection} class="py-20">
    <div class="container space-y-16">
        
             <HeadLine text="Tudo pensado para o seu bem-estar!"/>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 ">
            {#each products as {image, title, description, specification}}
            <div class="border-personalized grid grid-cols-1 justify-between border-1 border-green-pea-800 gap-4 overflow-clip">
                <div >
                 <img  src= "/image/products/{image.name}.webp" alt={image.alt}>
                </div>
                 <div class="p-5 space-y-4 text-green-pea-950">
                   <h3>{title}</h3>
                   {#each description as itens }
                     <p>{itens}</p>
                   {/each}
                   <div class="flex flex-wrap gap-2">
                   {#each specification as itens }
                   <span class="text-xs border border-green-950/50 py-2 px-3 rounded-full "> {itens}</span>
    
                   {/each}
                   </div>
                   
                 </div>
            </div>    
            {/each}
        </div>
        <div>
            <BoxIcons/>
        </div>
    </div>
</section>