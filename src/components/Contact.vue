<template>
  <section id="contact" class="main-container section-panel mt-16 py-16 md:mt-24 md:py-24 lg:mt-32 lg:py-28">
    <span class="section-label">Contato</span>
    <h2 class="mt-3 text-[27px] font-bold leading-tight tracking-[-0.01em] text-[var(--nd-text)] md:text-[32px]">
      Vamos construir algo juntos?
    </h2>
    <p class="mt-3 max-w-2xl text-[15px] text-[var(--nd-text-muted)] md:text-[16px]">
      Conte seu projeto ou desafio. Respondemos em até 24 horas.
    </p>

    <div class="mt-6 grid gap-5 md:mt-8 md:gap-7 lg:grid-cols-[1.12fr_0.88fr]">
      <form class="surface rounded-2xl p-6 md:p-7" @submit.prevent="submitForm">
        <div class="grid gap-4 md:grid-cols-2">
          <label class="field">
            <span class="field-label">Nome</span>
            <input
              v-model="form.name"
              type="text"
              name="name"
              required
              class="field-input"
              placeholder="Seu nome"
            />
          </label>

          <label class="field">
            <span class="field-label">E-mail</span>
            <input
              v-model="form.email"
              type="email"
              name="email"
              required
              class="field-input"
              placeholder="voce@empresa.com"
            />
          </label>
        </div>

        <label class="field mt-4 block">
          <span class="field-label">Mensagem</span>
          <textarea
            v-model="form.message"
            name="message"
            rows="6"
            required
            class="field-input min-h-[140px] resize-y"
            placeholder="Fale sobre seu projeto"
          ></textarea>
        </label>

        <button
          type="submit"
          :disabled="isLoading"
          class="btn-primary mt-5 inline-flex w-full items-center justify-center rounded-lg px-5 py-2.5 text-sm font-medium disabled:cursor-not-allowed disabled:opacity-60 sm:w-auto"
        >
          {{ isLoading ? "Enviando..." : "Enviar" }}
        </button>

        <p v-if="statusMessage" class="mt-4 text-sm" :class="statusType === 'success' ? 'text-emerald-300' : 'text-rose-300'">
          {{ statusMessage }}
        </p>
      </form>

      <aside class="surface rounded-2xl p-6 md:p-7">
        <img src="/logo_escrita_NorthDev.png" alt="North Dev" class="mb-5 h-9 w-auto opacity-95" />
        <h3 class="text-[18px] font-bold text-[var(--nd-text)]">Canais alternativos</h3>
        <div class="mt-4 space-y-3">
          <a href="https://wa.me/5500000000000" target="_blank" rel="noopener noreferrer" class="channel-link">
            <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
              <path d="M8 1.5C4.41 1.5 1.5 4.39 1.5 7.96C1.5 9.39 1.96 10.72 2.75 11.8L2.07 14.5L4.86 13.77C5.89 14.47 7.12 14.88 8.45 14.88C12.04 14.88 14.95 11.99 14.95 8.42C14.95 4.84 11.59 1.5 8 1.5Z" stroke="currentColor" stroke-width="1.2"/>
              <path d="M5.5 6.2C5.7 5.9 6 5.9 6.2 6.1L7.1 7C7.3 7.2 7.3 7.4 7.2 7.6L6.8 8.2C7 8.8 7.6 9.4 8.3 9.8L8.9 9.4C9.1 9.3 9.3 9.3 9.5 9.5L10.4 10.4C10.6 10.6 10.6 10.9 10.3 11.1C9.7 11.6 8.9 11.8 8.1 11.6C6.3 11.1 4.9 9.8 4.4 8C4.2 7.2 4.4 6.5 5 5.9" stroke="currentColor" stroke-width="1.2" stroke-linecap="round"/>
            </svg>
            WhatsApp
          </a>

          <a href="mailto:contato@northdev.com" class="channel-link">
            <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
              <rect x="1.5" y="3" width="13" height="10" rx="1.8" stroke="currentColor" stroke-width="1.2"/>
              <path d="M2.5 4L8 8L13.5 4" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
            contato@northdev.com
          </a>

          <a href="https://www.linkedin.com/company/northdev" target="_blank" rel="noopener noreferrer" class="channel-link">
            <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
              <rect x="1.5" y="1.5" width="13" height="13" rx="2" stroke="currentColor" stroke-width="1.2"/>
              <path d="M5 7V11" stroke="currentColor" stroke-width="1.2" stroke-linecap="round"/>
              <path d="M5 5.2C5.14 5.2 5.25 5.09 5.25 4.95C5.25 4.81 5.14 4.7 5 4.7C4.86 4.7 4.75 4.81 4.75 4.95C4.75 5.09 4.86 5.2 5 5.2Z" fill="currentColor"/>
              <path d="M8 11V8.7C8 8.06 8.49 7.6 9.13 7.6C9.77 7.6 10.2 8.06 10.2 8.7V11" stroke="currentColor" stroke-width="1.2" stroke-linecap="round"/>
              <path d="M8 7.3V7" stroke="currentColor" stroke-width="1.2" stroke-linecap="round"/>
            </svg>
            LinkedIn
          </a>
        </div>
      </aside>
    </div>
  </section>
</template>

<script setup>
import { reactive, ref } from "vue";

const form = reactive({
  name: "",
  email: "",
  message: "",
});

const isLoading = ref(false);
const statusMessage = ref("");
const statusType = ref("success");

async function submitForm() {
  if (isLoading.value) {
    return;
  }

  isLoading.value = true;
  statusMessage.value = "";

  try {
    const response = await fetch("https://formspree.io/f/SEU_ID", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Accept: "application/json",
      },
      body: JSON.stringify({
        name: form.name,
        email: form.email,
        message: form.message,
      }),
    });

    if (!response.ok) {
      throw new Error("Falha no envio");
    }

    statusType.value = "success";
    statusMessage.value = "Mensagem enviada com sucesso. Retornaremos em breve.";
    form.name = "";
    form.email = "";
    form.message = "";
  } catch (error) {
    statusType.value = "error";
    statusMessage.value = "Não foi possível enviar agora. Tente novamente em instantes.";
  } finally {
    isLoading.value = false;
  }
}
</script>

<style scoped>
.field {
  display: flex;
  flex-direction: column;
  gap: 0.45rem;
}

.field-label {
  font-size: 12px;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  color: var(--nd-text-subtle);
}

.field-input {
  border-radius: 0.7rem;
  border: 1px solid transparent;
  background: rgba(255, 255, 255, 0.04);
  padding: 0.72rem 0.88rem;
  font-size: 15px;
  color: var(--nd-text);
  transition: border-color 0.2s ease, background 0.2s ease;
}

.field-input:focus {
  outline: none;
  border-color: var(--nd-border-blue);
  background: rgba(37, 99, 235, 0.07);
}

.channel-link {
  display: inline-flex;
  align-items: center;
  gap: 0.6rem;
  font-size: 14px;
  color: var(--nd-text-muted);
  transition: color 0.2s ease;
}

.channel-link:hover {
  color: var(--nd-text);
}
</style>
