# ✈️ playwright-on-flight

[![Playwright Tests (CI/CD)](https://github.com/tiagonline/playwright-on-flight/actions/workflows/playwright.yml/badge.svg)](https://github.com/tiagonline/playwright-on-flight/actions/workflows/playwright.yml)
[![API Tests (Postman/Newman)](https://github.com/tiagonline/playwright-on-flight/actions/workflows/api-tests.yml/badge.svg)](https://github.com/tiagonline/playwright-on-flight/actions/workflows/api-tests.yml)

**Projeto de Automação Full Stack (Web & API) para Avaliação Técnica - Onfly**

**Candidato:** Tiago Silva

---

## 📋 Sobre o Projeto

Teste técnico e estruturei um plano de automação E2E em **Playwright + TypeScript**.

- Usei o **Page Object Model (POM)** para garantir alta manutenibilidade e a metodologia **BDD** para tornar os testes legíveis por QAs e PMs.  
- O projeto já inclui pipelines de **CI/CD** (Web e API), provando que a solução é escalável e está pronta para ser integrada ao processo de entrega contínua da Onfly.

---

## 💡 Decisões de Arquitetura

1. **Page Object Model (POM):** Separação total entre a lógica do teste e os seletores da página, facilitando a manutenção.  
2. **BDD Style:** Uso de `test.step` para criar relatórios que funcionam como **documentação viva** dos cenários.  
3. **Full Stack QA:**
   - **Web (Playwright):** Testes E2E de fluxo crítico (Checkout) com cenários positivos, negativos e de exceção.  
   - **API (Postman/Newman):** Testes de integração de CRUD com validação de contrato e dados dinâmicos.  
4. **CI/CD (GitHub Actions):** Pipelines automatizados para Web e API com geração de artefatos (Reports) e segurança de tokens (Secrets).

---

## 💻 Como Executar

### 🧩 Pré-requisitos

- Node.js (v18+)
- Playwright Browsers (instalado via `npm init playwright`)

---

### 1️⃣ Instalação

Clone o repositório e instale as dependências:

```bash
git clone https://github.com/tiagonline/playwright-on-flight.git
cd playwright-on-flight
npm install
npx playwright install --with-deps
```

---

### 2️⃣ Rodar Testes Web (Playwright)

Para validar o fluxo E2E de Checkout:

#### ▶️ Executar testes (Headless)

```bash
npx playwright test
```

#### 📊 Visualizar relatório (Trace Viewer)

```bash
npx playwright show-report
```

---

### 3️⃣ Rodar Testes de API (Newman)

Para validar o CRUD de Usuários (GoRest):

> **Nota:** É necessário ter o newman instalado ou usar via `npx`.

#### ▶️ Executar via npx (sem instalação global)

```bash
npx newman run tests/api/GoRest_CRUD.postman_collection.json   -e tests/api/GoRest_Env.postman_environment.json   --reporters cli,htmlextra
```

---

## ✅ Próximos Passos (Visão de Futuro)

Para evoluir este projeto em um ambiente de produção na Onfly, minha estratégia seria:

1. **Integração com Xray/Jira:** Conectar o relatório de testes para visibilidade total do time de gestão.  
2. **Contract Testing (Pact):** Implementar testes de contrato nas APIs críticas para garantir que mudanças no Backend não quebrem o Frontend ou Mobile.  
3. **Performance no Pipeline:** Integrar testes de carga com K6 diretamente no CI para validar a performance de endpoints críticos (ex: busca de passagens).  
4. **IA & Self-Healing:** Explorar recursos de IA para "auto-correção" de seletores (self-healing), visando reduzir o custo de manutenção dos scripts a longo prazo.
