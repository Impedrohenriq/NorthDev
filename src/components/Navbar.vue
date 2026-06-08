<template>
  <header class="fixed inset-x-0 top-0 z-50 bg-[rgba(7,13,26,0.72)] backdrop-blur-md">
    <div class="main-container flex h-[72px] w-full items-center justify-between">
      <a href="#" class="group inline-flex items-center" aria-label="North Dev home">
        <img src="/logo_escrita_NorthDev.png" alt="North Dev" class="hidden h-9 w-auto transition-all duration-200 ease-in-out group-hover:brightness-110 md:block" />
        <img src="/logo_northDev.png" alt="North Dev" class="h-10 w-10 rounded-md transition-all duration-200 ease-in-out group-hover:brightness-110 md:hidden" />
      </a>

      <nav class="hidden items-center gap-8 md:flex">
        <a href="#about" class="nav-link">Sobre</a>
        <a href="#projects" class="nav-link">Projetos</a>
        <a href="#contact" class="nav-link">Contato</a>
      </nav>

      <a href="#contact" class="btn-primary hidden rounded-lg px-4 py-2 text-sm font-medium md:inline-flex">
        Fale Conosco
      </a>

      <button
        type="button"
        class="inline-flex h-10 w-10 items-center justify-center rounded-md bg-[rgba(255,255,255,0.03)] text-[var(--nd-text-muted)] transition-all duration-200 ease-in-out hover:bg-[rgba(37,99,235,0.15)] hover:text-[var(--nd-text)] md:hidden"
        aria-label="Abrir menu"
        @click="isOpen = !isOpen"
      >
        <svg v-if="!isOpen" width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <path d="M3 5H15" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
          <path d="M3 9H15" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
          <path d="M3 13H15" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
        </svg>
        <svg v-else width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <path d="M4.5 4.5L13.5 13.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
          <path d="M13.5 4.5L4.5 13.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
        </svg>
      </button>
    </div>

    <div v-show="isOpen" class="bg-[rgba(7,13,26,0.9)] px-4 py-4 md:hidden">
      <nav class="main-container flex flex-col gap-2">
        <a href="#about" class="mobile-link" @click="closeMenu">Sobre</a>
        <a href="#projects" class="mobile-link" @click="closeMenu">Projetos</a>
        <a href="#contact" class="mobile-link" @click="closeMenu">Contato</a>
        <a href="#contact" class="btn-primary mt-2 inline-flex w-full items-center justify-center rounded-lg px-4 py-2 text-sm font-medium" @click="closeMenu">
          Fale Conosco
        </a>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";

const isOpen = ref(false);

function closeMenu() {
  isOpen.value = false;
}
</script>

<style scoped>
.nav-link {
  font-size: 14px;
  color: var(--nd-text-muted);
  transition: color 0.2s ease;
}

.nav-link:hover {
  color: var(--nd-text);
}

.mobile-link {
  border-radius: 0.65rem;
  padding: 0.55rem 0.7rem;
  color: var(--nd-text-muted);
  font-size: 14px;
  background: rgba(255, 255, 255, 0.025);
  transition: color 0.2s ease, background 0.2s ease;
}

.mobile-link:hover {
  color: var(--nd-text);
  background: rgba(37, 99, 235, 0.12);
}
</style>
