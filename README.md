# Projeto Pulse Mais — Plataforma de Fechamento de Feedbacks (ClearIT)

Este repositório contém a documentação e os artefatos da Prova de Conceito (PoC) desenvolvidos para a ClearIT. Remodelamos o escopo do projeto para eliminar qualquer barreira de privacidade ou gravação de voz.

Nossa solução agora é uma **Plataforma de Fechamento Co-construído de 1:1 e Feedbacks**. Nos 5 minutos finais da reunião, líder e liderado respondem a um questionário rápido de Sim/Não e preenchem um campo dissertativo-argumentativo com os acordos. A IA processa esses dados para gerar os relatórios do Líder e do RH.

---

## 📌 Links Rápidos da Nova Estrutura

### 📂 Pasta `docs/` (Planejamento e Negócio)
* 📄 [Contexto Técnico Lite - Etapa 2](docs/technical-context-lite.md) — Engenharia de prompts e testes focados em analisar formulários e textos dissertativos.

### 📂 Pasta `src/` (Arquitetura do MVP)
* 🛠️ [Templates de Prompts (JSON)](src/prompts_templates.json) — Configuração de como a IA lê o formulário para gerar os relatórios.
* 📊 [Exemplo de Entrada de Formulário (JSON)](src/mock_form_input.json) — Modelo das respostas de Sim/Não e do texto dissertativo coletados no app.
* 📱 [Fluxo de Interface (UI/UX)](src/interface_flow.md) — Mapeamento das telas do questionário quinzenal e dos dashboards.
