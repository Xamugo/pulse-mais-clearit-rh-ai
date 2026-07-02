# Contexto Técnico Lite — Etapa 2 (PoC de Formulários + IA)

## 1. Escopo de Testes da PoC
Para garantir a privacidade dos colaboradores da ClearIT e seguir as orientações acadêmicas, testamos a viabilidade técnica de uma IA processar um **módulo de fechamento quanti-qualitativo**. 
A IA recebe o resultado de perguntas fechadas (Sim/Não) e um texto dissertativo resumido pelo líder, gerando duas saídas:
1. **Para o Líder:** Feedback estruturado em formato SBI.
2. **Para o RH:** Relatório macro de prontidão de carreira (Júnior para Pleno/Sênior), barreiras comportamentais e status de PDI.

Todos os testes foram feitos com **dados 100% fictícios**, mitigando riscos de vazamento e respeitando a LGPD.

## 2. Tecnologias Avaliadas
* **Processamento de Inputs Estruturados:** Validação de formulários JSON.
* **Modelo de Linguagem (LLM):** Engenharia de prompts aplicada sobre textos dissertativos-argumentativos de fechamento.

## 3. Engenharia de Prompts e Evidências

### Teste de Processamento (Formulário + Dissertação)
* **Prompt da IA:**
  > "Você é um analista de RH e suporte à liderança. Receba as respostas binárias e a dissertação de fechamento de uma 1:1. Gere: 1) O relatório SBI para o Líder; 2) Um indicador para o RH avaliando se o colaborador apresenta barreiras comportamentais e se está pronto para subir de nível (ex: Pleno para Sênior). Ignore assuntos pessoais."
* **Input Simulado:**
  * *Pergunta 1 (As entregas estão no prazo?):* SIM
  * *Pergunta 2 (Sente sobrecarga ou barreira externa?):* NÃO
  * *Dissertação do Líder:* "O colaborador demonstrou excelente autonomia na última sprint. Ele liderou a apresentação técnica para o cliente ontem, mostrando maturidade comportamental e domínio do framework. Está cumprindo todos os combinados do PDI e já atua com postura de Sênior nas reuniões."
* **Output Esperado da IA:**
  * **Relatório SBI (Líder):**
    * *Situação:* Apresentação técnica para o cliente ontem.
    * *Comportamento:* Liderou a reunião com autonomia e maturidade comportamental.
    * *Impacto:* Demonstração de domínio técnico e alinhamento com o nível Sênior.
  * **Relatório Executivo (RH):**
    * *Status do PDI:* Ativo e com metas cumpridas.
    * *Barreiras Comportamentais:* Nenhuma detectada.
    * *Prontidão de Carreira:* Alta probabilidade de elegibilidade para promoção de nível (Pleno para Sênior).
