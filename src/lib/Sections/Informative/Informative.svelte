<script>
    let informative =  {
        title: "Aloe Vera",
        text1: "O extrato de aloe vera atua no combate de rugas e envelhecimento da pele. Além de manter a pele firme e ultramacia.",
        text2: "Contém vitaminas, proteínas e sais minerais que penetram facilmente na camada externa da pele nutrindo e hidratando.",
    }
</script>

<section class="py-20">
    <div class="container grid grid-cols-1 lg:grid-cols-2 p-6 gap-15 justify-center items-center  bg-green-pea-800">
      <div class="lg:h-[315px] rounded-3xl overflow-clip">
        <img src="/image/informative/section-informative-creme-aloe-vera.webp" alt="">
      </div>
      <div class="flex flex-col gap-8 text-green-pea-50">
        <h2 class="titleSection">{informative.title}</h2>
        <p class="text-2xl">{informative.text1}</p>
        <p class="text-2xl">{informative.text2}</p>
      </div>
    </div>
</section>