<template>
  <section class="hero-wrap relative overflow-hidden pt-26 md:pt-30">
    <div class="hero-glow pointer-events-none absolute inset-0"></div>
    <div class="main-container grid items-center gap-10 pb-10 md:grid-cols-2 md:gap-16 md:pb-16 lg:gap-20 lg:pb-18">
      <div class="pt-6 md:pt-10">
        <span class="mb-4 inline-flex text-[11px] uppercase tracking-[0.1em] text-[var(--nd-blue-light)]">
          Desenvolvimento de Software
        </span>

        <h1 class="text-[34px] leading-[1.05] font-extrabold tracking-[-0.02em] text-[var(--nd-text)] md:text-[50px] lg:text-[56px]">
          Build. Automate.
          <span class="text-[var(--nd-blue-light)]">Scale</span>. North.
        </h1>

        <p class="mt-5 max-w-xl text-[15px] text-[var(--nd-text-muted)] md:text-[16px]">
          A North Dev constrói software moderno, automações poderosas e produtos SaaS escaláveis que guiam seu negócio na direção certa.
        </p>

        <div class="mt-7 flex flex-col gap-2.5 sm:flex-row sm:items-center">
          <a href="#projects" class="btn-primary inline-flex w-full items-center justify-center rounded-lg px-5 py-2.5 text-sm font-medium sm:w-auto">
            Ver Projetos
          </a>
          <a href="#contact" class="btn-soft inline-flex w-full items-center justify-center rounded-lg px-5 py-2.5 text-sm font-medium sm:w-auto">
            Agendar Conversa ->
          </a>
        </div>

        <div class="mt-7 grid grid-cols-3 gap-2.5 text-center sm:max-w-md">
          <div class="px-2 py-1.5">
            <p class="text-[20px] font-bold text-[var(--nd-text)]">+20</p>
            <p class="text-[11px] uppercase tracking-[0.08em] text-[var(--nd-text-subtle)]">Projetos</p>
          </div>
          <div class="px-2 py-1.5 border-x border-[rgba(255,255,255,0.12)]">
            <p class="text-[20px] font-bold text-[var(--nd-text)]">24h</p>
            <p class="text-[11px] uppercase tracking-[0.08em] text-[var(--nd-text-subtle)]">Resposta</p>
          </div>
          <div class="px-2 py-1.5">
            <p class="text-[20px] font-bold text-[var(--nd-text)]">100%</p>
            <p class="text-[11px] uppercase tracking-[0.08em] text-[var(--nd-text-subtle)]">Custom</p>
          </div>
        </div>
      </div>

      <div class="relative mx-auto w-full max-w-[460px]">
        <div class="logo-shell surface rounded-2xl p-5 md:p-8">
          <img src="/logo_northDev.png" alt="Logo North Dev" class="logo-anim mx-auto w-full max-w-[360px]" />
        </div>
      </div>
    </div>

    <div class="main-container mb-2 pb-8 md:pb-12">
      <div class="tech-bar rounded-xl px-3 py-3 md:px-4">
        <ul class="flex flex-wrap items-center justify-center gap-2 text-[11px] text-[var(--nd-text-subtle)] md:text-[13px]">
          <li v-for="(tech, index) in techStack" :key="tech" class="inline-flex items-center">
            <span>{{ tech }}</span>
            <span v-if="index < techStack.length - 1" class="mx-2 opacity-45">•</span>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
const techStack = ["Vue 3", ".NET", "Node.js", "Oracle", "PWA", "TailwindCSS"];
</script>

<style scoped>
.hero-wrap {
  background-image: radial-gradient(circle at 25% 15%, rgba(96, 165, 250, 0.11), transparent 45%);
}

.hero-wrap::after {
  content: "";
  position: absolute;
  inset: 0;
  background-image: radial-gradient(rgba(138, 160, 192, 0.26) 1px, transparent 1px);
  background-size: 22px 22px;
  opacity: 0.12;
  pointer-events: none;
}

.hero-glow {
  background: radial-gradient(circle at 70% 30%, rgba(37, 99, 235, 0.22), transparent 35%);
}

.logo-shell {
  box-shadow: var(--nd-shadow-lg);
}

.logo-anim {
  animation: floatY 4.6s ease-in-out infinite;
}

.tech-bar {
  backdrop-filter: blur(2px);
}

@keyframes floatY {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-8px);
  }
  100% {
    transform: translateY(0px);
  }
}
</style>
