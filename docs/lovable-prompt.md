# Prompt Mestre para o Lovable — Atualização para MPB (Melhor para o Brasil)

Copie e cole o prompt abaixo no campo de chat do Lovable para reestruturar e implementar todas as funcionalidades da aplicação **MPB (Melhor para o Brasil)** de uma só vez, garantindo economia de tokens e alinhamento com as novas especificações técnicas:

---

## PROMPT PARA O LOVABLE:

"Por favor, reestruture e renomeie a nossa aplicação para **MPB (Melhor para o Brasil)**, seguindo rigorosamente as especificações abaixo. O design visual deve seguir a identidade estética da **Clear IT** (https://clearit.com.br/) de forma fiel:
*   **Estilo:** Leve, limpo, minimalista, sem ruídos e com muito espaçamento (white space). Use cantos ligeiramente arredondados (`rounded-md`, `border-radius: 6px` a `8px`) e design plano/flat, sem sombras de caixa marcadas (`box-shadow: none` ou `shadow-sm` muito suave).
*   **Logotipo e Paleta de Cores:**
    *   *Logo:* Utilize o arquivo local `logo-mpb.png` no cabeçalho e na tela de login (ícone circular com globo, gráfico de linhas e seta ascendente em verde e amarelo; texto 'MPB' em azul-escuro e '(Melhor para o Brasil)' abaixo).
    *   *Fundo Geral:* `#F4F4F4` (off-white muito suave) ou `#FFFFFF` (branco puro).
    *   *Fundo Secundário/Cards:* `#E5E3E3` (cinza-claro neutro) ou `#FFFFFF`.
    *   *Texto e Cabeçalhos (Deep Navy):* `#292658` (azul-marinho profundo elegante da logo).
    *   *Ações Primárias e Realce:* Tons suaves e degradês de verde-bandeira e amarelo/ciano de forma sutil para botões principais, links, focos e barras de progresso.
    *   *Ações Secundárias e Tags:* `#8F8AE0` (lavanda/roxo suave).
    *   *Bordas e Divisores:* `#E0E0E0` (cinza ultra sutil).
*   **Tipografia:** Títulos em `"Titillium Web"` ou `"Inter"` (moderna e geométrica), e o corpo de texto em `"Roboto"` ou `"Inter"`.
*   Toda a persistência de dados e estado de login/sessão deve continuar sendo feita via `localStorage`.
*   **Estrutura de Rotas:** A aplicação deve ser dividida em duas áreas fundamentais:
    1.  *Portal de Lançamento e Repositório (Rota principal `/` ou `index.html`):* Funciona como vitrine do projeto, abrigando um simulador interativo de repositório Git e o Manual de Uso.
    2.  *MVP da Aplicação (Rota `/app` ou `app.html`):* Contém os fluxos operacionais de login (Líder, Liderado, RH), preenchimento, relatórios e dashboards.


### 1. Níveis de Acesso e Tela de Login (`/login` ou `/`)
*   Adicione ou atualize a tela de Login para diferenciar três níveis de acesso com as seguintes credenciais padrão:
    *   **Líder:** `lider@empresa.com` (Senha: `123`, Nome: Ana Silva) -> Acesso ao painel de preparação, fechamento e histórico de seus liderados.
    *   **Liderado:** `colaborador@empresa.com` (Senha: `123`, Nome: Diego Santos) -> Acesso a seu próprio histórico e assinatura digital de termos pendentes.
    *   **RH:** `rh@empresa.com` (Senha: `123`, Nome: Mariana Souza) -> Portal analítico de RH (People Analytics) com visão de indicadores globais.
*   Crie botões de preenchimento rápido para cada perfil na tela de login para facilitar os testes rápidos.
*   No cabeçalho, exiba as opções de navegação correspondentes a cada perfil e a opção de 'Sair' (Logout).
*   **Dados Iniciais (Mock Seeding):** Se o `localStorage` estiver vazio ao abrir o aplicativo, inicialize-o com dados fictícios ricos:
    *   3 líderes cadastrados (Ana Silva, Carlos Souza, Beto Lima).
    *   3 liderados cadastrados vinculados a Ana Silva: `COL-01` (Diego Santos, Level L2, Tecnologia, com 1:1 há 0 dias), `COL-02` (Erika Reis, Level L1, Design, sem histórico de 1:1 há 45 dias) e `COL-03` (Felipe Dias, Level L3, Produto, sem histórico de 1:1 há 60 dias).
    *   Um histórico simulado de pelo menos três reuniões 1:1 concluídas e assinadas para o `COL-01` para fins de gráfico e relatórios individuais, além de pelo menos quatro avaliações bidirecionais trocadas com comentários textuais de diferentes tons para testar a moderação de IA.

### 1.5. Tela de Preparação de 1:1 (`/preparar` - Exclusivo do Líder)
*   **Exibição ao selecionar colaborador no dropdown:**
    *   *Identificação:* Nome completo, Função e Setor/Área correspondente.
    *   *Competências Esperadas:* Exibir as competências baseadas em Level (L1: Autonomia e aprendizado; L2: Resolução independente de problemas e mentoria; L3: Liderança técnica e impacto de negócio).
    *   *Pautas Recomendadas (Evolução de Carreira):* Exibir 2 assuntos ou perguntas sugeridas focadas no progresso profissional e passos para o próximo nível de carreira do colaborador.

### 2. Reformulação do Formulário de 1:1 (`/fechamento` - Exclusivo do Líder)
*   Substitua as perguntas atuais por **5 perguntas obrigatórias de Sim ou Não**.
*   **Perguntas Variáveis:** As perguntas devem apresentar formulações variáveis (sinônimos que mudam dinamicamente a cada carregamento) mantendo exatamente o mesmo cunho e sentido original (Evolução/PDI, Gargalo Técnico, Alinhamento Cultural, Necessidade de Evolução, Suporte do Líder).
*   **Campos de Texto Condicionais Opcionais:** Ao acionar um campo de texto adicional por resposta de atenção, esse campo deve ser **completamente opcional** e **não deve ter limite mínimo de caracteres** (validação livre).
*   **Wording e Ações de Atenção:**
    1.  **Entregas e Resultados:** *"O liderado atingiu as principais metas combinadas?"* (ou variações). Se **Não** -> *"O que faltou para a entrega?"* (Opcional, sem mínimo de caracteres).
    2.  **Alinhamento Cultural:** *"O liderado demonstrou comportamentos alinhados aos valores?"* (ou variações). Se **Não** -> *"Qual comportamento precisa ser corrigido?"* (Opcional, sem mínimo de caracteres).
    3.  **Necessidade de Evolução:** *"Identificou algum gargalo/ponto de desenvolvimento?"* (ou variações). Se **Sim** -> *"Descreva a situação."* (Opcional, sem mínimo de caracteres).
    4.  **Suporte do Líder:** *"O liderado possui alguma barreira externa impedindo sua evolução?"* (ou variações). Se **Sim** -> *"Como ajudar a destravar?"* (Opcional, sem mínimo de caracteres).
    5.  **Foco no Futuro (PDI):** *"Ficou definido o plano de ação?"* (ou variações). Se **Sim** -> *"Quais as principais ações combinadas?"* (Opcional, sem mínimo de caracteres).
*   **Observações Gerais:** Área dissertativa opcional no final (máximo 500 caracteres).
*   **Botão 'Enviar para Análise':** Habilita imediatamente após as 5 respostas de Sim/Não serem preenchidas, sem obrigar digitação nos campos opcionais. A mensagem de carregamento deve ser: *"A IA da MPB está estruturando e moderando o seu feedback..."*.
*   **LGPD:** Exiba o aviso de privacidade garantindo confidencialidade dos relatos detalhados.

### 3. Integração com IA (SBI e Moderação de Tom)
*   **Gemini API Key:** Mantenha o modal de configuração de chave no cabeçalho. Se não configurado, use o mock com delay de 2 segundos.
*   **Consolidação inteligente e Diretrizes de IA:** A IA deve cruzar as respostas do formulário para estruturar o feedback formal no formato **SBI (Situation, Behavior, Impact - Situação, Comportamento, Impacto)** mais **Recomendações de PDI**.
    *   **CRÍTICO - CONSISTÊNCIA DE CONTEÚDO:** A IA (e o motor de Sandbox local de mock) deve refletir fielmente a **verdade factual da avaliação**. Se o líder marcou **NÃO** para cumprimento de metas, alinhamento de valores ou inseriu críticas de baixo desempenho nas observações, a IA **NUNCA** deve florear ou criar contradições positivas (como afirmar que o colaborador manteve engajamento exemplar ou recomendar PDI de promoção para o próximo nível de senioridade). A IA deve manter o diagnóstico de gap de performance, mas traduzido em tom corporativo, polido e focado em um plano de melhoria e recuperação imediata de entregas.
*   **Moderação de Tom, LGPD e Direitos Humanos:**
    *   A IA atua como um guardião estrito de conformidade à LGPD e aos Direitos Humanos.
    *   Ela analisa as anotações do líder, detecta e remove de forma absoluta qualquer linguagem inadequada, agressiva, rude, hostil ou depreciativa.
    *   **Higienização de Dados Sensíveis e Proteção à Saúde (LGPD):** Qualquer informação que exponha diagnósticos de saúde específicos (como "depressão"), nomes de médicos, psicólogos ou clínicas deve ser totalmente omitida para proteção de dados sensíveis. Contudo, em vez de ignorar a situação do colaborador, a IA deve **generalizar e apoiar a questão**, registrando que o colaborador relatou estar enfrentando *'desafios pessoais de saúde'* ou *'questões temporárias de bem-estar/saúde mental'*.
    *   **Reconstrução para Crítica Construtiva e Apoio:** Toda queixa ou comentário ríspido deve ser transformado em um feedback construtivo rico e formal, com foco em desenvolvimento. A recomendação de PDI deve incluir, de forma empática e respeitosa, ações de acolhimento e suporte, direcionando a colaboradora aos programas de assistência interna da empresa ou sugerindo/encorajando que busque suporte de saúde especializado e profissional.
    *   **Exemplo Prático de Transformação (A IA e a simulação de Mock devem seguir este padrão exato):**
        *   *Texto de Entrada do Líder:* *"A Ana foi muito devagar e preguiçosa nessa sprint. Ela é muito burra e não consegue entender coisas simples. Além disso, ela fica de fofoca sobre a depressão dela com o psicólogo João Silva da Clínica X. Quero que melhore ou vou demitir."*
        *   *Saída Higienizada, Estruturada e Empática pela IA:*
            *   *Situação:* *"Durante a execução do ciclo recente de desenvolvimento técnico da equipe."*
            *   *Comportamento:* *"A colaboradora apresentou oscilações no ritmo de entrega e dificuldades na absorção de instruções operacionais, relatando desafios pessoais de saúde que têm impactado suas atividades cotidianas."*
            *   *Impacto:* *"Esse cenário afetou temporariamente o cronograma final do projeto e exigiu esforço adicional de suporte e redistribuição de tarefas entre o time."*
            *   *Recomendação de PDI:* *"Fornecer suporte técnico contínuo e checkpoints diários para acompanhamento próximo, oferecer maior flexibilidade de prazos nas próximas tarefas e orientá-la com empatia a buscar apoio profissional de saúde ou canais de assistência interna da empresa, priorizando seu bem-estar integral durante o processo de recuperação de desempenho."*
*   **Simulação de Fallback (Mock):** Caso a API Key não esteja configurada, a simulação de fallback local deve aplicar exatamente essa lógica de mapeamento rica. Ela deve ler a entrada do usuário e, se detectar termos negativos, informais ou referências de saúde, deve sanitizá-los e convertê-los em alternativas formais e empáticas no formato SBI + PDI conforme o exemplo prático acima.
*   Ao terminar, redirecione para a **Nova Tela de Revisão SBI**.

### 4. Revisão, Assinatura e Autenticação (`/revisao-sbi` e `/meu-painel`)
*   **Aviso de Conformidade:** Exiba o banner informando que o líder humano é o único responsável pelo feedback final.
*   **Campos Editáveis:** 4 textareas contendo as seções geradas pela IA (Situação, Comportamento, Impacto, Recomendações de PDI) que o líder pode ajustar antes de assinar.
*   **Assinatura do Líder:** Campo no rodapé para assinatura digital eletrônica (digitar o nome ou desenhar). Ao salvar, muda o status para `Pendente de Assinatura do Liderado`.
*   **Assinatura do Liderado (Autenticação):** Ao logar, o liderado abre o feedback pendente, visualizando **apenas a Análise SBI estruturada e moderada por IA (LGPD/DH)** (Situação, Comportamento, Impacto e Recomendações de PDI), omitindo as perguntas Sim/Não e os rascunhos originais do líder. Ele aceita o Termo de Ciência e clica para assinar.
*   **Token de Autenticação:** Abre um modal simulando o envio de um código de verificação para o e-mail do liderado. Exiba o código na tela para testes rápidos. O liderado digita o token para autenticar e assinar digitalmente. O status muda para `Concluído e Assinado`.

### 5. Geração de PDF e Simulador de E-mail
*   Assim que finalizado e assinado por ambos, o sistema deve:
    1.  Gerar um PDF estruturado (usando a biblioteca `jspdf`) contendo **apenas a Análise SBI estruturada e moderada por IA (LGPD/DH)** (Situação, Comportamento, Impacto e Recomendações de PDI), metadados de cabeçalho e os logs de assinaturas. Não inclua no PDF as perguntas binárias nem os rascunhos originais do líder.
    2.  Simular o disparo de e-mail enviando este PDF para o e-mail do Liderado (Toast de notificação).
    3.  Disponibilizar uma aba **'Simulador de E-mails'** no rodapé/menu para o usuário verificar a caixa de entrada do colaborador e abrir/baixar o PDF gerado diretamente com o assunto *"Seu Relatório de 1:1 - MPB"*.

### 6. Área de Feedback Bidirecional (`/feedback-bidirecional`)
*   **Formulários com Moderação por IA:** Líder e Liderado respondem a avaliações mútuas periódicas (5 perguntas de 1 a 5 estrelas sobre cooperação, comunicação e suporte + campo de texto opcional). Qualquer comentário textual digitado deve obrigatoriamente passar pela **mesma inteligência artificial de moderação e correção de tom (LGPD/DH)** para converter queixas em sugestões de desenvolvimento construtivas.
*   **Privacidade e Acesso do RH:** Os feedbacks bidirecionais salvos são privados e confidenciais, visíveis apenas para os envolvidos e acessíveis exclusivamente pelo time de RH na aba de Gestão Pessoal por ID anonimizado. Qualquer texto de comentário visível ao RH deve passar obrigatoriamente pela moderação/correção de tom da IA (respeitando LGPD/DH).
*   **Histórico:** Permita que ambos visualizem o histórico de feedbacks bidirecionais privados trocados entre si.
 
### 7. Ajustes no Dashboard do RH (`/dashboard-rh`)
*   **Anonimização Estrita (LGPD):** O RH visualiza dados agregados por gráficos e tabelas de auxílio geral e IDs anonimizados (ex: `COL-01`) para preservar dados de saúde e privacidade.
*   **Acompanhamento de Cadência (Tabela e Ações):**
    *   Exiba a tabela **"Acompanhamento de cadência"** listando o ID do colaborador (ex: `COL-01`), o perfil (`Level L1/L2/L3 · Área`), a informação de dias desde a última 1:1 (ex: `Último 1:1 há 0 dia(s)` ou `Último 1:1 há —`), um badge de status (`Risco de cadência` se sem 1:1 há mais de 30 dias, ou `Em dia`) e um botão **"Abrir >"**.
    *   **CRÍTICO - NAVEGAÇÃO DO BOTÃO ABRIR:** Clicar no botão **"Abrir >"** de qualquer colaborador da tabela de cadência deve encaminhar o usuário diretamente para a rota da página de detalhes individuais dele: `/dashboard-rh/colaborador/:id`.
*   **Gráficos e Indicadores:**
    *   **Gráfico de Cadência:** Exiba o gráfico de barras **"Cadência de 1:1 (dias desde o último)"** com barras para cada colaborador (`COL-01`, `COL-02`, etc.), pintando as barras de amarelo/vermelho caso haja risco de atraso (mais de 30 dias).
    *   **Card de Feedback Bidirecional:** Exiba a média geral de estrelas em avaliações de liderança (ex: `2.2 / 5`) e uma caixa **"COMPILAÇÃO DA IA"** com um resumo gerado pela IA consolidando os pontos mais importantes para o desenvolvimento corporativo.
*   **Área de Gestão Pessoal (Reports Singulares - Rota `/dashboard-rh/colaborador/:id`):**
    *   **CRÍTICO - SEPARAÇÃO DE ROTAS:** A rota `/dashboard-rh/colaborador/:id` (onde `:id` representa o colaborador selecionado, ex: `u-colab-1` ou `COL-01`) **deve ser uma view/página totalmente distinta e independente** da página principal `/dashboard-rh`. Não reutilize o mesmo layout ou componente de lista do dashboard para esta rota. Crie um componente dedicado e exclusivo contendo um botão de voltar visível ("Voltar para o Dashboard") e os seguintes blocos para análise do RH:
        1.  *Histórico Completo:* Lista das reuniões 1:1 realizadas ao longo do tempo (datas e líder).
        2.  *Assuntos Abordados:* Lista dos temas e assuntos debatidos em cada encontro (ex: prazos, PDI, carreira).
        3.  *Feedback do Líder sobre o Liderado:* O feedback do líder formatado em SBI e higienizado pela IA sob as travas da LGPD e Direitos Humanos (neutralizando ofensas e genericizando menções a problemas de saúde como "desafios pessoais de saúde" ou sugestões empáticas de suporte psicológico).
        4.  *Evolução de PDI:* Barra de progresso visual de conclusão de metas de PDI (ex: 'Progresso de PDI: 80%').
        5.  *Mapeamento de Levels (L1, L2, L3):* Comparação das competências exigidas pelo nível contra as competências atendidas no histórico para calibrar a progressão.
        6.  *Feedbacks Bidirecionais Singulares:* Lista das avaliações mútuas individuais trocadas pelo colaborador (enviadas e recebidas com estrelas e texto), com todos os comentários textuais moderados/corrigidos pela IA (respeitando LGPD/DH).

### 8. Manual do Sistema Integrado (Acessível via Menu em `/app`)
*   Adicione o link **"Manual & Sobre"** no menu do cabeçalho da aplicação `/app.html` para todos os perfis (Líder, Liderado, RH).
*   Ao clicar nesse link, o sistema deve exibir uma tela estilizada contendo o manual técnico-operacional do sistema estruturado da seguinte forma:
    1.  *Descrição do Sistema:* Finalidade de aproximar a liderança de suas equipes por People Analytics e SBI estruturado.
    2.  *Principais Funcionalidades:* Lista contendo a descrição das features desenvolvidas.
    3.  *Não Funcional (Mocks):* Detalhamento das limitações técnicas do protótipo (SMTP simulado, API sandbox local sem API Key, dados em localStorage).
    4.  *Sugestões de Evoluções:* Próximos passos e melhorias de arquitetura.
    5.  *Equipe e Grupo:* Nome do grupo e integrantes.

### 9. Portal de Lançamento e Repositório Git (Acessível via `/` ou `index.html`)
*   A página raiz da aplicação (`index.html`) deve ser uma vitrine contendo uma navegação limpa baseada em abas com os seguintes conteúdos:
    1.  *Aba 🏠 Lançamento:* Apresenta a marca MPB Conexão Humana, valor estratégico, métricas chaves e botões de chamada de ação para iniciar o MVP funcional.
    2.  *Aba 💻 Repositório Git:* Interface que simula de forma visual a estrutura de repositório no GitHub para `joaos/mpb-conexao-humana`. Contém uma barra lateral com a árvore de arquivos do projeto (`site/app.html`, `site/index.html`, `docs/lovable-prompt.md`, `docs/business-context-lite.md`, `README.md`) e um visualizador de código interativo que carrega o código/descrição de cada arquivo selecionado, além de uma sub-aba mostrando o histórico dos commits recentes realizados.
    3.  *Aba 📖 Manual & Sobre:* Exibe o manual completo do sistema estruturado (com as 5 seções descritas na seção anterior)."

