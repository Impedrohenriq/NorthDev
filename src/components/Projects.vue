<template>
  <section id="projects" class="main-container section-panel mt-12 py-16 md:mt-18 md:py-24 lg:mt-24 lg:py-28">
    <span class="section-label">Portfólio</span>
    <h2 class="mt-3 text-[27px] font-bold leading-tight tracking-[-0.01em] text-[var(--nd-text)] md:text-[32px]">
      Projetos em destaque
    </h2>

    <div class="mt-6 grid gap-4 md:mt-8 lg:grid-cols-2">
      <article class="surface card-hover rounded-2xl p-6 md:p-7 lg:col-span-2">
        <span class="tag tag-blue">PWA · Offline-First</span>
        <h3 class="mt-3 text-[22px] font-bold text-[var(--nd-text)] md:text-[28px]">CPTM Ambiental</h3>
        <p class="mt-3 max-w-3xl text-[15px] text-[var(--nd-text-muted)] md:text-[16px]">
          Sistema de controle ambiental de efluentes para inspeções de campo. Funciona offline e sincroniza automaticamente ao reconectar. Vue 3 + .NET + Oracle.
        </p>
        <div class="mt-4 flex flex-wrap gap-x-3 gap-y-1">
          <span v-for="tech in highlightedTech" :key="tech" class="chip">{{ tech }}</span>
        </div>
      </article>

      <article class="surface card-hover rounded-2xl p-6 md:p-7">
        <span class="tag tag-amber">Automação</span>
        <h3 class="mt-3 text-[20px] font-bold text-[var(--nd-text)]">Sync Engine</h3>
        <p class="mt-2 text-[15px] text-[var(--nd-text-muted)]">
          Motor de sincronização robusto para sistemas críticos com gestão de estado e retry automático.
        </p>
        <div class="mt-4 flex flex-wrap gap-x-3 gap-y-1">
          <span v-for="tech in syncTech" :key="tech" class="chip">{{ tech }}</span>
        </div>
      </article>

      <article class="surface card-hover rounded-2xl p-6 md:p-7">
        <span class="tag tag-green">SaaS</span>
        <h3 class="mt-3 text-[20px] font-bold text-[var(--nd-text)]">Seu projeto aqui</h3>
        <p class="mt-2 text-[15px] text-[var(--nd-text-muted)]">
          Desenvolvimento personalizado conforme as necessidades do seu negócio.
        </p>
        <a href="#contact" class="mt-4 inline-flex text-[14px] font-medium text-[var(--nd-blue-light)] transition-all duration-200 ease-in-out hover:text-[var(--nd-text)]">
          Solicitar orçamento ->
        </a>
      </article>
    </div>
  </section>
</template>

<script setup>
const highlightedTech = [
  "Vue 3",
  "Pinia",
  ".NET",
  "Oracle DB",
  "IndexedDB",
  "TailwindCSS",
];

const syncTech = ["TypeScript", "Node.js", "REST API"];
</script>

<style scoped>
.card-hover {
  transition: background 0.2s ease, box-shadow 0.2s ease, transform 0.2s ease;
}

.card-hover:hover {
  background: rgba(37, 99, 235, 0.08);
  transform: translateY(-2px);
  box-shadow: 0 22px 44px -30px rgba(37, 99, 235, 0.72);
}

.tag {
  display: inline-flex;
  font-size: 11px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

.tag-blue {
  color: #bfdbfe;
  text-shadow: 0 0 16px rgba(96, 165, 250, 0.45);
}

.tag-green {
  color: #d1fae5;
  text-shadow: 0 0 14px rgba(16, 185, 129, 0.45);
}

.tag-amber {
  color: #fde68a;
  text-shadow: 0 0 14px rgba(245, 158, 11, 0.45);
}

.chip {
  font-size: 12px;
  color: var(--nd-text-subtle);
  position: relative;
}

.chip::after {
  content: "";
  display: inline-block;
  width: 4px;
  height: 4px;
  margin-left: 10px;
  border-radius: 999px;
  background: rgba(96, 165, 250, 0.45);
  transform: translateY(-1px);
}

.chip:last-child::after {
  display: none;
}
</style>
