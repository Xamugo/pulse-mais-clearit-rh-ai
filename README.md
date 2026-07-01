# Projeto Pulse Mais - Solução de IA para Gestão de Liderança (ClearIT)

Este repositório contém a documentação estratégica, técnica, os artefatos e a prova de conceito (PoC) desenvolvidos para a otimização de processos de RH, engajamento e retenção de lideranças na ClearIT.

A solução consiste em uma plataforma mobile/web capaz de registrar reuniões de 1:1 e Feedbacks via áudio, transformando transcrições brutas em inteligência de liderança e relatórios analíticos densos para o setor de People Analytics[cite: 1].

---

## 🗺️ Fluxo de Funcionamento da Solução (PoC/MVP)

Abaixo está mapeado o fluxo de inteligência da nossa aplicação, demonstrando como a gravação de voz se transforma em ferramentas práticas para o Líder e visibilidade estratégica para o RH[cite: 1]:

![Fluxo de Inteligência de 1:1 e Feedback](fluxo-poc.png)

---

## 📌 Links Rápidos da Documentação

### 📂 Pasta `docs/` (Regras de Negócio e Planejamento)
* 📄 [Contexto de Negócio Lite - Etapa 1](docs/business-context-lite.md) — Mapeamento do problema de retenção, ausência de registros e dores da ClearIT[cite: 1].
* ⚙️ [Contexto Técnico Lite - Etapa 2](docs/technical-context-lite.md) — Engenharia de prompts testada, massas de dados fictícios para validação de IA e conformidade com LGPD[cite: 1].

### 📂 Pasta `src/` (Arquitetura Técnica do MVP)
* 🛠️ [Templates de Prompts (JSON)](src/prompts_templates.json) — Estrutura de código simulando onde as instruções de IA ficam armazenadas no sistema.
* 💬 [Transcrição de Teste (Massa de Dados)](src/mock_transcription.txt) — Exemplo de áudio bruto convertido em texto utilizado para validar os motores de LLM[cite: 1].
* 📱 [Fluxo de Interface e Telas (UI/UX)](src/interface_flow.md) — Mapeamento da jornada visual do Líder e do painel de People Analytics do RH[cite: 1].

---

## 👥 Integrantes do Projeto
* João, Pedro, Gustavo, Nathalia, Mikael

---

## 🎯 Objetivo da Sprint Atual
Validar com o cliente e com a banca acadêmica a viabilidade técnica da extração de dados através de Inteligência Artificial e Engenharia de Prompts[cite: 1]. Provamos de forma isolada (PoC) que dados não estruturados de áudio podem gerar relatórios de aderência ao modelo SBI para líderes e People Analytics profundo para o RH, sem violar a privacidade e com mascaramento de dados sensíveis[cite: 1].

---
*Nota: Todos os dados apresentados e testados nesta fase são simulados e fictícios, conforme os requisitos da PoC da Sprint 2.*
