# Fluxo de Telas do Aplicativo — Especificação de Interface (UI/UX)

Este documento especifica os controles visuais, regras de validação client-side, estados de erro e layouts de cada tela do **Pulse Mais**, servindo como especificação exata de desenvolvimento de frontend.

---

## 🔐 Tela 0: Login e Níveis de Acesso [US00]

Esta tela gerencia as permissões de acesso da plataforma e divide a experiência do usuário em três perfis distintos.

*   **Controles de Entrada (Inputs):**
    *   Dropdown `SelectPerfil`: Seleção entre "Líder", "Liderado" e "RH".
    *   Dropdown `SelectUsuario`: Filtra a lista de usuários fictícios disponíveis no seed data com base no perfil selecionado para simplificar o login na PoC.
    *   Campo `InputSenha`: Senha simples simulada para o login do usuário.
*   **Controles de Ação:**
    *   Botão `Entrar`: Valida as credenciais locais no `localStorage` e direciona para a área correspondente com transição animada.

---

## 📱 Área do Líder e Liderado (Jornada Síncrona de 1:1)

### Tela 1: Preparação da Reunião [US01]

Esta tela permite que o líder estruture a conversa antes do encontro presencial.

*   **Controles de Entrada (Inputs):**
    *   Dropdown `SelectColaborador`: Menu de seleção de colaboradores vinculados ao líder logado.
*   **Elementos de Exibição (Outputs Dinâmicos):**
    *   Label `CargoLiderado`: Exibe o cargo e nível do colaborador selecionado (ex: *"Cargo: Desenvolvedor Júnior (L1)"*).
    *   Painel `CompetenciasLevels`: Lista de competências associadas ao nível do framework do colaborador.
    *   Painel `PautasSugeridas`: Exibe 2 perguntas de pauta geradas de acordo com o nível (L1, L2, ou L3).
*   **Controles de Ação:**
    *   Botão `IniciarReuniao`: Direciona para a Tela 2. Fica desabilitado até selecionar um colaborador.

---

### Tela 2: Questionário de Fechamento (Os 5 minutos finais) [US02]

Tela onde o líder registra as respostas às 5 perguntas de Sim/Não e dissertações condicionais.

*   **Controles de Entrada (Inputs):**
    *   Cards de Rádios para as 5 perguntas obrigatórias (Sim/Não):
        1.  *Entregas e Resultados:* "O liderado atingiu as principais metas/entregas combinadas para este período?" (Se **Não**, abre Textarea `EntregaDetalhe` com placeholder *"O que faltou para a entrega?"*).
        2.  *Alinhamento Cultural:* "O liderado demonstrou comportamentos alinhados aos valores da cultura da empresa?" (Se **Não**, abre Textarea `CulturaDetalhe` com placeholder *"Qual comportamento precisa ser corrigido?"*).
        3.  *Necessidade de Evolução:* "Identificou algum gargalo ou ponto de desenvolvimento (técnico ou comportamental) que precisa de ajuste imediato?" (Se **Sim**, abre Textarea `EvolucaoDetalhe` com placeholder *"Descreva a situação ou comportamento a ser corrigido."*).
        4.  *Suporte do Líder:* "O liderado possui alguma barreira ou obstáculo externo impedindo sua evolução atual?" (Se **Sim**, abre Textarea `SuporteDetalhe` com placeholder *"Como o líder ou a empresa podem ajudar a destravar?"*).
        5.  *Foco no Futuro (PDI):* "Ficou claro e definido o plano de ação/próximos passos do liderado até o próximo encontro?" (Se **Sim**, abre Textarea `PdiDetalhe` com placeholder *"Quais as principais ações combinadas?"*).
    *   Área de Texto `InputObservacoesGerais`: Opcional, ao final do formulário para anotações livres, elogios ou observações extras.
*   **Elementos de Exibição:**
    *   Contadores dinâmicos de caracteres para cada campo de texto condicional exibido.
*   **Controles de Ação:**
    *   Botão `EnviarParaAnalise`: Habilitado apenas quando as 5 perguntas estiverem respondidas e os campos condicionais abertos estiverem preenchidos. Abre overlay *"IA processando feedback síncrono..."* e redireciona para a Tela 3.

---

### Tela 3: Revisão do Feedback SBI & Moderação de Tom [US03]

Conferência do retorno da IA com moderação de tom aplicada.

*   **Alerta Informativo:**
    *   *Texto:* "⚠️ Lembre-se: O líder humano é o único responsável pelo feedback final. Revise as sugestões da IA e edite o que for necessário."
*   **Controles de Entrada (Inputs Editáveis):**
    *   Textareas contendo: `EditSituacao`, `EditComportamento`, `EditImpacto` e `EditPDI` (sugestão de PDI).
    *   Textarea `EditFeedbackModerado`: Feedback geral moderado pela IA para atenuar linguagem agressiva.
*   **Controles de Ação:**
    *   Botão `ProsseguirAssinatura`: Salva o rascunho do feedback estruturado e inicia a etapa de assinatura.

---

### Tela 4: Assinatura e Autenticação [US04]

Termo de ciência e fluxo de assinaturas digitais.

*   **Elementos de Exibição:**
    *   Termo de ciência obrigatório afirmando concordância com a reunião de feedback.
*   **Assinatura do Líder:**
    *   Opção de desenho no Canvas ou digitada com fonte cursiva.
*   **Assinatura e Autenticação do Liderado:**
    *   Botão `EnviarTokenEmail`: Simula o envio de um token de 6 dígitos via e-mail. Um popup exibe o token simulado (ex: *"📧 Token enviado: 482910"*).
    *   Campo `InputToken`: O liderado digita o token para desbloquear seu campo de assinatura digital (desenho ou digitada).
*   **Controles de Ação:**
    *   Botão `FinalizarReuniao`: Registra as assinaturas e hashes no banco de dados e dispara a geração e o envio do PDF.

---

### Tela 5: Caixa de Entrada Simulada do Liderado [US05]

Simulador de caixa de e-mails do colaborador para validar o recebimento do feedback.

*   **Elementos de Exibição:**
    *   Lista de e-mails simulados recebidos pelo Liderado ativo.
    *   E-mail de assunto: *"Registro de 1:1 e Feedback — ClearIT"*.
    *   Conteúdo do e-mail com resumo e botão para baixar/visualizar o PDF gerado pela biblioteca `jspdf`.

---

## 📊 Portal do RH (Dashboard Analítico)

### Tela 6: Painel de People Analytics & LGPD [US06]

Painel de controle com acesso macro restrito para o RH.

*   **Controles de Filtro:**
    *   Dropdown `FiltroArea`: Opções: Tecnologia, Design, Produto, Geral.
*   **Matriz de Métricas e Clima:**
    *   Cards de KPI: Taxa de Aderência à Cadência, Percentual de Gargalos de Infraestrutura, e Dificuldades Técnicas.
    *   Lista de Prontidão de Carreira: Tabela exibindo os IDs anonimizados (ex: `COL-01`) marcados pela IA como elegíveis para promoção.
    *   Lista de Alertas de Risco: Exibe colaboradores sem 1:1 há mais de 30 dias ou com flags de risco de turnover acesas.
*   **Regra de LGPD:**
    *   Tabelas omitem nomes reais e textos de feedback detalhados do líder, exibindo apenas dados anonimizados e relatórios de métricas.



