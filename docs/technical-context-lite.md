# Contexto Técnico Lite - Etapa 2 (PoC)

## 1. Escopo de Testes da PoC (O que foi testado)
Para validar a viabilidade técnica da solução para a ClearIT de forma isolada, focamos em testar o fluxo de inteligência artificial que recebe a **gravação/transcrição de áudio** de uma reunião e gera dois outputs distintos:
1. **Para o Líder:** Um plano de ação rápido estruturado no modelo SBI (Situação, Comportamento, Impacto)[cite: 1].
2. **Para o RH:** Um relatório denso e analítico contendo métricas de clima, riscos de turnover e lacunas de competências detectadas na conversa de forma anonimizada.

Conforme as restrições de riscos mapeadas, todos os testes foram realizados utilizando **dados 100% fictícios**, garantindo total conformidade com a LGPD e regras de privacidade do RH[cite: 1].

## 2. Arquitetura Tecnológica Avaliada
* **Speech-to-Text (Transcrição de Áudio):** Tecnologia avaliada para transformar a gravação de voz da 1:1 em texto corrido automaticamente.
* **Modelo de Linguagem (LLM):** Motor de IA testado via Engenharia de Prompts para ler a transcrição bruta e gerar os relatórios do Líder e do RH[cite: 1].

## 3. Engenharia de Prompts e Resultados (Evidências)

### Teste 1: Transcrição Bruta $\rightarrow$ Relatório Denso para o RH
* **Prompt Utilizado pela IA:**
  > "Aja como um Analista de RH Sênior especialista em People Analytics. Leia a transcrição bruta da reunião de 1:1 fictícia abaixo. Extraia e gere um relatório denso contendo: 1) Índice de Energia/Bem-estar do colaborador (0 a 10), 2) Principais obstáculos sistêmicos citados, 3) Competências do Framework de Levels trabalhadas e 4) Alerta de Risco de Turnover (Baixo, Médio, Alto) com a justificativa. Remova nomes reais e dados médicos."
* **Transcrição Bruta de Teste (Áudio Simulado):**
  > "Cara, então, a gente tá na metade da sprint e eu tô me sentindo muito sobrecarregado porque a equipe de infraestrutura atrasou a entrega do ambiente e eu tô tendo que fazer hora extra pra compensar. Na parte de comunicação com o cliente eu sinto que melhorei, consegui apresentar a última demo sozinho, mas o ambiente tá foda, se continuar nessa pressão de entregas travadas por outras áreas eu não sei quanto tempo aguento nesse projeto."
* **Output gerado pela IA (Relatório do RH):**
  * **1) Índice de Bem-estar:** 4/10 (Sinais claros de sobrecarga por fatores externos).
  * **2) Obstáculos Sistêmicos:** Dependência e gargalo na entrega da equipe de infraestrutura, gerando retrabalho e horas extras.
  * **3) Competências do Framework de Levels:** Evolução positiva detectada em *Comunicação com Stakeholders* (Apresentou a demo sozinho).
  * **4) Alerta de Risco de Turnover:** **MÉDIO-ALTO**. O colaborador sinalizou insatisfação com a pressão contínua e mencionou limite de permanência caso o cenário sistêmico não mude.

### Teste 2: Transcrição Bruta $\rightarrow$ Feedback Estruturado para o Líder (Modelo SBI)
* **Prompt Utilizado pela IA:**
  > "Com base na mesma transcrição, gere para o Líder um resumo executivo focado em desenvolvimento, organizando os combinados no formato SBI e garantindo que haja um espaço de co-construção do próximo passo."
* **Output gerado pela IA:**
  * **Situação:** Alinhamento da metade da sprint[cite: 1].
  * **Comportamento:** O liderado assumiu a responsabilidade de apresentar a demo sozinho para o cliente e buscou compensar os atrasos[cite: 1].
  * **Impacto:** Evolução na autonomia de comunicação, mas com alto desgaste de energia individual[cite: 1].
  * **Acordo/Próximo Passo:** O gestor vai intervir diretamente junto ao time de infraestrutura para remover o obstáculo antes da próxima reunião quinzenal[cite: 1].

## 4. Alinhamento e Escopo do MVP (Aplicativo)
Com o sucesso da PoC de prompts, o escopo definido para a construção do aplicativo será[cite: 1]:
* **Interface:** Aplicativo Web/Mobile com um botão simples de "Gravar Reunião"[cite: 1].
* **Processamento:** O app grava o áudio, envia para a API de transcrição e roda os prompts validados nesta PoC de forma automática[cite: 1].
* **Segurança (Guardrails):** Mascaramento automático de dados pessoais antes do relatório ser enviado para o banco de dados do RH, respeitando estritamente a LGPD[cite: 1].
