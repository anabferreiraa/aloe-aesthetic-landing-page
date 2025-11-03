<script>
  const productBenefits = [
    {
      icon: {
        dir: "/image/icons/",
        name: "icon-natural-product",
        alt: "Produto 98% natural"
      },
      title: "Produto 98% natural."
    },
    {
      icon: {
        dir: "/image/icons/",
        name: "biodegradable-packaging",
        alt: "Embalagem biodegradável"
      },
      title: "Embalagem biodegradável"
    },
    {
      icon: {
        dir: "/image/icons/",
        name: "icon-not-tested-on-animals",
        alt: "Não testado em animais"
      },
      title: "Não testado em animais"
    },
    {
      icon: {
        dir: "/image/icons/",
        name: "icon-dermatologically-tested",
        alt: "Dermatologicamente testado"
      },
      title: "Dermatologicamente testado"
    }
  ];

</script>

<section class="grid grid-cols-1 md:grid-cols-3 items-center mt-20 gap-10">
  <!-- Coluna esquerda -->
  <div class="flex flex-col items-center justify-center gap-20">
    {#each productBenefits.slice(0, 2) as { icon, title }}
      <div class="flex flex-col items-center text-center gap-2">
        <div class="relative w-20 h-20">
  <!-- Borda girando -->
  <div class="absolute inset-0 border-5 border-dashed border-green-900 rounded-full animate-spin-slow"></div>

  <!-- Imagem fixa -->
  <img
    class="w-full h-full rounded-full relative"
    src={icon.dir + icon.name + ".svg"}
    alt={icon.alt}
  />
</div>
        <p class="text-green-pea-800 text-lg">{title}</p>
      </div>
    {/each}
  </div>

  <!-- Coluna central (imagem principal) -->
  <div class="flex justify-center">
    <img
      src="/image/products/product-benefits.webp"
      alt="Produtos Aloe Aesthetic"
      class="max-w-md w-full object-contain"
    />
  </div>

  <!-- Coluna direita -->
  <div class="flex flex-col items-center justify-center gap-20">
    {#each productBenefits.slice(2, 4) as { icon, title }}
      <div class="flex flex-col items-center text-center gap-2">
        <div class="relative w-20 h-20">
  <!-- Borda girando -->
  <div class="absolute inset-0 border-5 border-dashed border-green-900 rounded-full animate-spin-slow"></div>

  <!-- Imagem fixa -->
  <img
    class="w-full h-full rounded-full relative"
    src={icon.dir + icon.name + ".svg"}
    alt={icon.alt}
  />
</div>
        <p class="text-green-pea-800 text-lg">{title}</p>
      </div>
    {/each}
  </div>
</section>
