<template>
  <section id="about" class="main-container section-panel py-16 md:py-24 lg:py-28">
    <span class="section-label">Sobre a empresa</span>
    <h2 class="mt-3 text-[27px] font-bold leading-tight tracking-[-0.01em] text-[var(--nd-text)] md:text-[32px]">
      Progredindo na direção certa.
    </h2>

    <div class="mt-5 grid gap-8 md:mt-7 lg:grid-cols-[1.1fr_1fr] lg:items-start lg:gap-10">
      <div class="max-w-2xl space-y-4 text-[15px] text-[var(--nd-text-muted)] md:text-[16px]">
        <p>
          Nossa missão é ajudar empresas a avançarem com clareza estratégica usando software sob medida, automações inteligentes e produtos digitais sustentáveis no longo prazo.
        </p>
        <p>
          A North Dev combina visão de produto, engenharia moderna e foco em resultados para construir soluções que simplificam operações, reduzem gargalos e criam novas possibilidades de crescimento.
        </p>
        <a href="#contact" class="mt-3 inline-flex rounded-lg border border-[var(--nd-border-blue)] px-4 py-2 text-sm font-medium text-[var(--nd-text)] transition-all duration-200 ease-in-out hover:bg-[var(--nd-bg-surface)]">
          Fale com a gente
        </a>
      </div>

      <div class="grid gap-3 sm:grid-cols-2">
        <article v-for="pillar in pillars" :key="pillar.title" class="surface group rounded-xl p-4 transition-all duration-200 ease-in-out hover:border-[var(--nd-border-blue)] hover:bg-[rgba(37,99,235,0.08)] md:p-5">
          <div class="mb-3 inline-flex h-11 w-11 overflow-hidden rounded-xl bg-[rgba(37,99,235,0.15)] shadow-[0_10px_20px_-16px_rgba(96,165,250,0.8)]">
            <img :src="pillar.image" :alt="`Imagem ${pillar.title}`" class="h-full w-full object-cover" />
          </div>
          <h3 class="text-[18px] font-bold text-[var(--nd-text)]">{{ pillar.title }}</h3>
          <p class="mt-1.5 text-[14px] text-[var(--nd-text-subtle)]">{{ pillar.description }}</p>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
const pillars = [
  {
    title: "Desenvolvimento",
    description: "Software customizado com tecnologias modernas.",
    image: "/about-dev.png",
  },
  {
    title: "Automação",
    description: "Workflows inteligentes que eliminam tarefas repetitivas.",
    image: "/about-automation.png",
  },
  {
    title: "Produtos SaaS",
    description: "Plataformas escaláveis para resolver problemas reais.",
    image: "/about-saas.png",
  },
  {
    title: "Crescimento",
    description: "Foco em resultado, não só em código.",
    image: "/about-growth.png",
  },
];
</script>

<style scoped>
</style>
