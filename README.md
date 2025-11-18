# 🚀 playwright-on-flight
**Projeto de Automação E2E para Avaliação Técnica - Onfly**

**Candidato:** Tiago Oliveira Silva

**Objetivo:** Atender a solicitação do desafio técnico: **Definir casos de testes e criar a automação E2E (Ponta a Ponta) para um fluxo de compras de e-commerce utilizando Playwright** (sem finalizar a compra).

---

## 💡 1. Decisões de Arquitetura

Este projeto foi construído em **Playwright (TypeScript)**, escolhido por sua estabilidade em CI/CD e velocidade.

1.  **Page Object Model (POM):** Arquitetura utilizada para garantir **manutenibilidade** e **separação de responsabilidades**. O teste lê como uma história do usuário, e a manutenção dos seletores é centralizada (Design Pattern essencial que a Fernanda irá gostar).
2.  **BDD Style:** As etapas de teste foram definidas usando `test.step` para que o relatório (rodar `npx playwright show-report`) funcione como **documentação viva** (BDD Style), facilitando o entendimento para Stakeholders e QAs.
3.  **CI/CD (DevOps):** O projeto já inclui um pipeline básico (no `.github/workflows/playwright.yml`) para rodar os testes automaticamente no GitHub Actions.

## 💻 2. Requisitos & Execução

### Pré-requisitos
* Node.js (v18+)
* Playwright Browsers (instalado via `npm init playwright`)

### Execução
1.  Clone o repositório.
2.  Instale as dependências: `npm install`
3.  Execute o teste (Headless): `npx playwright test`
4.  Visualize o Relatório HTML: `npx playwright show-report`

---

## ✅ 3. Próximos Passos

Para levar este projeto para um ambiente de produção Onfly, os próximos passos seriam:

1.  **Integração com Xray/Jira:** Integrar o relatório de testes para que os cenários sejam visíveis no painel de gestão de testes da equipe (Xray é usado na Onfly).
2.  **Mocks & Fixtures:** Migrar os dados de Login e Checkout para o arquivo de Fixtures do Playwright para maior segurança e reuso de dados.
3.  **API Testing:** Adicionar o módulo de testes de API (Backend) no mesmo pipeline para garantir a qualidade de ponta a ponta (mesmo com a API ServeRest fora do ar, o design do teste já estaria pronto).