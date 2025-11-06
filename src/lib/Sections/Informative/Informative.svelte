<script>
   const idSection = "sobre"
    let informative =  {
        title: "Aloe Vera",
        text: [
             "O poder da natureza para a sua pele.",
             "O extrato de Aloe Vera ajuda a combater rugas e os sinais de envelhecimento, mantendo a pele firme, suave e radiante.",
             "Rico em vitaminas, proteínas e sais minerais, penetra facilmente nas camadas da pele, proporcionando nutrição profunda e hidratação duradoura.",
        ] 
    }
</script>

<section id={idSection} class="py-20 bg-green-pea-900">
    <div class="container grid grid-cols-1 lg:grid-cols-2 p-6 gap-20 justify-center items-center">
      <div class="lg:h-[315px] border-personalized overflow-clip">
        <img loading="lazy" src="/image/informative/section-informative-creme-aloe-vera.webp" alt="">
      </div>
      <div class="flex flex-col gap-4 text-green-pea-50">
        <h2 class="">{informative.title}</h2>
        {#each informative.text as text }
          <p class="">{text}</p>
        {/each}
        
      </div>
    </div>
</section>