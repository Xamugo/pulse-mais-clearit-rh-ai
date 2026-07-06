# Fluxo de Telas do Aplicativo — Especificação de Interface (UI/UX)

Este documento especifica os controles visuais, regras de validação client-side, estados de erro e layouts de cada tela do **Pulse Mais**, servindo como especificação exata de desenvolvimento de frontend.

---

## 📱 Fluxo do Líder e Liderado (Jornada Síncrona de 1:1)

### Tela 1: Preparação da Reunião [US01]
Esta tela permite que o líder estruture a conversa antes do encontro presencial.

*   **Controles de Entrada (Inputs):**
    *   Dropdown `SelectColaborador`: Menu de seleção de funcionários vinculados ao líder logado.
        *   *Placeholder:* "Selecione um liderado..."
*   **Elementos de Exibição (Outputs Dinâmicos):**
    *   Label `CargoLiderado`: Exibe o cargo e nível do colaborador selecionado (ex: *"Cargo: Desenvolvedor Júnior (L1)"*).
    *   Painel `CompetenciasLevels`: Caixa de texto com bordas que apresenta a lista de competências comportamentais e técnicas associadas ao nível do Framework de Levels do colaborador.
    *   Painel `PautasSugeridas`: Exibe 2 perguntas de pauta geradas de acordo com as regras:
        *   *Para L1 (Júnior):* 1. Pergunta sobre autonomia diária na sprint. 2. Pergunta sobre colaboração no time.
        *   *Para L2 (Pleno):* 1. Pergunta sobre mentoria de iniciantes. 2. Pergunta sobre resolução autônoma de problemas técnicos.
        *   *Para L3 (Sênior):* 1. Pergunta sobre impacto arquitetural no negócio. 2. Pergunta sobre facilitação técnica coletiva.
*   **Controles de Ação:**
    *   Botão `IniciarReuniao`:
        *   *Texto:* "Iniciar Conversa (Ir para Fechamento)"
        *   *Regra de Validação:* Fica **Desabilitado** (opacidade 50%) até que um colaborador seja selecionado no dropdown. Fica **Habilitado** (verde sólido) após a seleção.

---

### Tela 2: Questionário de Fechamento (Os 5 minutos finais) [US02]
Tela onde o líder registra os dados da 1:1 que acabou de acontecer.

*   **Controles de Entrada (Inputs):**
    *   Card de Rádios `PerguntaPDI`:
        *   *Label:* "O Plano de Desenvolvimento Individual (PDI) está ativo e sendo seguido?"
        *   *Opções:* `SIM` (ID: `pdi_sim`) e `NÃO` (ID: `pdi_nao`).
    *   Card de Rádios `PerguntaInfra`:
        *   *Label:* "Existe algum gargalo de infraestrutura (acesso, hardware, licenças) travando o time?"
        *   *Opções:* `SIM` (ID: `infra_sim`) e `NÃO` (ID: `infra_nao`).
    *   Card de Rádios `PerguntaTech`:
        *   *Label:* "O colaborador apresentou dificuldades técnicas específicas nesta sprint?"
        *   *Opções:* `SIM` (ID: `tech_sim`) e `NÃO` (ID: `tech_nao`).
    *   Área de Texto `InputDissertacao`:
        *   *Label:* "Resumo Executivo da Reunião (Fatos de desempenho e combinados):"
        *   *Placeholder:* "Descreva brevemente o comportamento do colaborador nesta sprint. Cite fatos concretos e alinhamentos efetuados..."
        *   *Limites de Validação:* `minlength="100"` e `maxlength="1000"`.
*   **Elementos de Exibição:**
    *   Label `ContadorCaracteres`: Renderiza o tamanho atual do texto no formato `[caracteres]/1000`.
        *   *Estilo:* Fica em **vermelho** se o texto for menor que 100 caracteres; muda para **verde** quando atinge 100 caracteres; volta para **vermelho** ao bater o limite máximo de 1000.
*   **Controles de Ação:**
    *   Botão `EnviarParaAnalise`:
        *   *Texto:* "Enviar para Análise da IA"
        *   *Regra de Validação:* Fica **Desabilitado** até que as 3 perguntas de rádio tenham uma opção selecionada E a Área de Texto contenha pelo menos 100 caracteres.
        *   *Comportamento de Clique:* Dispara requisição HTTP `POST /api/meetings/close`. Exibe overlay translúcido de carregamento em tela cheia com um spinner e a mensagem: *"IA processando feedback síncrono..."*

---

### Tela 3: Revisão do Feedback SBI [US03]
Tela de conferência que consome a resposta da IA.

*   **Alerta Informativo:**
    *   *Texto:* "⚠️ Lembre-se: O líder humano é o único responsável pelo feedback final. Revise as sugestões da IA e edite o que for necessário." (Conformidade com RN03)
*   **Controles de Entrada (Inputs Editáveis com Retorno da IA):**
    *   Textarea `EditSituacao`: Campo contendo a Situação extraída pela IA (Editável).
    *   Textarea `EditComportamento`: Campo contendo o Comportamento extraído pela IA (Editável).
    *   Textarea `EditImpacto`: Campo contendo o Impacto extraído pela IA (Editável).
    *   Textarea `EditPDI`: Campo contendo a sugestão de plano prático de desenvolvimento (Editável).
*   **Controles de Ação:**
    *   Botão `SalvarConcluir`:
        *   *Texto:* "Salvar e Concluir Reunião"
        *   *Comportamento:* Salva os dados finais do formulário no banco de dados e redireciona à listagem inicial com mensagem de sucesso.
    *   Botão `ExportarPDF`:
        *   *Texto:* "Exportar PDF de Feedback"
        *   *Comportamento:* Invoca a biblioteca `jspdf` no frontend, gerando o PDF formatado do feedback SBI para impressão ou envio por e-mail para o liderado.

---

## 📊 Fluxo do RH (Dashboard Analítico)

### Tela 4: Painel de People Analytics [US04]
Tela de visualização restrita à Gerente de RH, consolidando métricas agregadas por setor.

*   **Controles de Filtro:**
    *   Dropdown `FiltroArea`: Filtra todas as métricas agregadas (Opções: Tecnologia, Design, Produto, Geral).
*   **Indicadores de Performance (Painel de Métricas):**
    *   Card `TaxaAderencia`: Porcentagem de reuniões realizadas no prazo da cadência (exibe alerta em vermelho caso a taxa do setor esteja abaixo de 70%).
    *   Card `PercentualGargalo`: Quantidade de 1:1s onde `gargalo_infraestrutura` foi assinalado como `SIM`.
    *   Card `PercentualDificuldade`: Quantidade de 1:1s onde `dificuldade_tecnica` foi assinalado como `SIM`.
*   **Painel de Calibração e Sucessão (Tabelas de Promoção):**
    *   Lista de Prontidão: Tabela exibindo os IDs anonimizados dos colaboradores sinalizados como elegíveis para promoção de nível (`ELEGIVEL_PLENO` ou `ELEGIVEL_SENIOR`), omitindo qualquer dado pessoal.
*   **Painel de Alertas de Clima e Turnover:**
    *   Tabela contendo os IDs de colaboradores sob alerta de cadência (sem 1:1 há mais de 30 dias) ou com a flag `sinalizacao_risco_turnover` marcada como `TRUE` pela IA, permitindo ao RH atuar de forma preditiva.


