# Prompt do Zero para o Lovable — Criando a Aplicação MPB (Melhor para o Brasil)

Copie e cole o prompt abaixo em um **novo projeto do zero no Lovable** para gerar a aplicação inteira, com todas as páginas, dados de teste persistentes e recursos de IA/PDF integrados de uma só vez:

---

## PROMPT DO ZERO PARA O LOVABLE:

"Crie uma aplicação web responsiva em React com Tailwind CSS e componentes shadcn/ui chamada **MPB (Melhor para o Brasil)**, um assistente de gestão de pessoas e feedback de reuniões 1:1 corporativas. A estética visual da aplicação deve ser inspirada no site da **Clear IT** (https://clearit.com.br/), com foco em leveza, minimalismo e suavidade. Adote uma paleta de cores limpas com fundo predominantemente claro (light background), cinza-claro para contornos e separações, azul-marinho profundo para textos/menus, e detalhes em ciano e azul-celeste suaves. Integre a logomarca da **MPB** (imagem `logo-mpb.png` localizada na pasta de assets/site) que traz um ícone de globo com gráfico ascendente e seta nas cores verde e amarelo, e a sigla 'MPB' em azul-escuro com '(Melhor para o Brasil)' abaixo. Toda a persistência de dados deve ser mantida localmente no `localStorage`.

### 1. Inicialização de Dados de Teste (Seed Data) e Níveis de Acesso
Ao carregar a aplicação pela primeira vez, inicialize no `localStorage` os dados fictícios estruturados abaixo para que as telas e fluxos estejam populados de imediato. Crie três perfis de usuários com credenciais padrão para testes rápidos no cabeçalho ou na tela de login:
*   **Líder:** `lider@empresa.com` (Senha: `123`). Nome: Ana Silva (Líder da área de Tecnologia). Tem acesso para preparar 1:1, preencher o formulário de fechamento, visualizar o histórico de feedbacks que emitiu para os seus liderados e assinar digitalmente os relatórios.
*   **Liderado (Colaborador):** `colaborador@empresa.com` (Senha: `123`). Nome: Diego Santos (Nível: L1 - Júnior, Líder: Ana Silva, Área: Tecnologia). Tem acesso para visualizar apenas o seu histórico pessoal de reuniões e assinar/autenticar feedbacks pendentes de ciência.
*   **RH (Global):** `rh@empresa.com` (Senha: `123`). Nome: Mariana Souza. Tem acesso exclusivo ao portal global de People Analytics para visualizar métricas, engajamento, frequência de encontros, clima e desenvolvimento das equipes.
*   **Dados de Colaboradores Fictícios (Liderados pela Líder Ana Silva):**
    *   `COL-01` (Diego Santos, Nível: L1 - Júnior, Área: Tecnologia, Última 1:1: há 35 dias - Alerta de Cadência!)
    *   `COL-02` (Fernanda Costa, Nível: L2 - Pleno, Área: Tecnologia, Última 1:1: há 10 dias)
    *   `COL-03` (Mariana Lima, Nível: L3 - Sênior, Área: Design, Última 1:1: há 5 dias)
    *   `COL-04` (Lucas Rocha, Nível: L2 - Pleno, Área: Produto, Última 1:1: há 20 dias)
*   **Histórico Existente:** Inicialize pelo menos 2 registros passados de 1:1 no histórico do Diego Santos (já finalizados e assinados) contendo notas e análises SBI estruturadas.

### 2. Fluxo de Autenticação (Tela de Login - `/login` ou `/`)
*   Crie uma tela de login moderna, elegante e intuitiva.
*   Adicione cards ou botões de preenchimento rápido (ex: 'Logar como Líder', 'Logar como Liderado', 'Logar como RH') para facilitar testes sem digitação manual de credenciais.
*   Ao efetuar o login com sucesso, redirecione o usuário de forma inteligente conforme o nível de acesso:
    *   **Líder** -> Painel do Líder (iniciar conversas, preparar reuniões, listar liderados).
    *   **Liderado** -> Painel do Colaborador (feedbacks recebidos, pendências de assinatura).
    *   **RH** -> Dashboard Global de RH (People Analytics).
*   No cabeçalho do sistema, exiba o nome do usuário ativo, seu papel (ex: Líder, RH) e um botão 'Sair' (Logout) para voltar ao login.

### 3. Cabeçalho, Navegação e Configurações Gerais
*   **Identidade Estética e Logotipo:** A aplicação chama-se **MPB (Melhor para o Brasil)**. Insira a logomarca da **MPB** (utilizando o arquivo local `logo-mpb.png`) no cabeçalho e na tela de login. A logomarca consiste em um ícone circular contendo um globo terrestre com linhas, um gráfico de linha interna ascendente e uma seta de crescimento apontando para o canto superior direito nas cores verde e amarelo, acompanhado do texto principal 'MPB' em azul-escuro e '(Melhor para o Brasil)' logo abaixo. A interface deve ser extremamente limpa, leve, minimalista e arejada, adotando os seguintes padrões visuais exatos:
    *   **Paleta de Cores:**
        *   *Cor de Fundo Geral:* `#F4F4F4` (off-white muito suave) ou `#FFFFFF` para criar telas com alto contraste e respiro.
        *   *Cor de Fundo Secundária/Sessões:* `#E5E3E3` (cinza-claro neutro) para demarcar cards ou áreas de cabeçalho secundárias.
        *   *Texto Principal e Cabeçalhos (Deep Navy):* `#292658` (azul-marinho profundo elegante da logo).
        *   *Realces e Ações Primárias:* Degradês e tons de verde-bandeira e amarelo/ciano de forma sutil para botões principais, links, barras de progresso e focos.
        *   *Status Secundários e Tags:* `#8F8AE0` (lavanda/roxo suave).
        *   *Bordas e Divisores:* `#E0E0E0` (cinza ultra sutil para demarcar cards, inputs e contornos).
    *   **Tipografia:** Use a fonte `"Titillium Web"` ou `"Inter"` (sans-serif moderna) para cabeçalhos e títulos com tamanho expressivo e peso bem definido (ex: `font-semibold` ou `font-normal`). Use a fonte `"Roboto"` ou `"Inter"` para o corpo de texto (body text) garantindo excelente legibilidade.
    *   **Elementos e Componentes:** Todos os cards, blocos e inputs devem ter um design plano (flat), com cantos ligeiramente arredondados (border-radius: `6px` a `8px`, equivalente a `rounded-md`/`rounded-lg`), bordas finas de `1px` em `#E0E0E0` e **sem sombras de caixa** (`box-shadow: none` ou `shadow-sm` muito suave), eliminando o ruído visual.
    *   **Botões:** Botões planos e limpos com fundo azul-marinho (`#292658`) ou ciano/verde, texto em branco, sem gradientes.
    *   **Inputs e Formulários:** Bordas de `1px solid #E0E0E0`. No estado de foco (`focus`), o input deve receber contorno em cor ciano ou verde sem efeitos de brilho/glow.
*   **Menu de Navegação:** Renderizado dinamicamente com base nas permissões do usuário logado:
    *   **Líder:** 'Início (Painel do Líder)', 'Preparar 1:1', 'Registrar Fechamento', 'Feedback Bidirecional', 'Histórico de Feedbacks'.
    *   **Liderado:** 'Início (Meus Feedbacks)', 'Feedback Bidirecional', 'Termos Pendentes'.
    *   **RH:** 'Portal do RH (Analytics)'.
*   Adicione um botão de 'Engrenagem' no canto direito do cabeçalho que abra um Modal de Configurações para salvar a `Google Gemini API Key` do usuário no `localStorage`.

### 4. Tela de Preparação de 1:1 (`/preparar` - Exclusivo do Líder)
*   O líder escolhe um colaborador liderado em um menu dropdown.
*   **Exibição de Detalhes do Liderado Selecionado:** Ao selecionar a pessoa, exiba dinamicamente os seguintes dados detalhados na tela:
    *   **Identificação:** Nome completo, Função (ex: Desenvolvedor Júnior, Designer Pleno) e Setor/Área (ex: Tecnologia, Design, Produto).
    *   **Competências Esperadas:** Um painel com as competências esperadas para o nível atual do colaborador, baseado no Framework de Levels (L1 - Júnior: Autonomia em tarefas simples e aprendizado contínuo; L2 - Pleno: Resolução independente de problemas complexos, mentoria de juniores e colaboração ativa; L3 - Sênior: Liderança técnica de projetos complexos, arquitetura e impacto de negócio de ponta a ponta).
    *   **Pautas/Temas Recomendados (Foco em Evolução de Carreira):** Apresente dois assuntos/perguntas sugeridas para serem abordadas na reunião 1:1 com foco exclusivo em evolução de carreira e passos de crescimento do profissional (ex: L1 -> 'Quais habilidades técnicas você deseja aprimorar no próximo trimestre para caminhar em direção ao nível pleno?' e 'Quais tarefas você gostaria de assumir de forma mais independente?'; L2 -> 'Como você avalia seu progresso na mentoria de outros colaboradores?' e 'Qual projeto de maior complexidade você se sente pronto para liderar?'; L3 -> 'Como você planeja expandir seu impacto estratégico no negócio no próximo semestre?' e 'Quais iniciativas você propõe para a evolução da arquitetura do nosso produto?').
*   Adicione o botão 'Iniciar Conversa' (verde) que direciona para o formulário de fechamento preenchendo os dados do liderado automaticamente.

### 5. Tela de Fechamento de Reunião (`/fechamento` - Exclusivo do Líder)
Substitua o formulário tradicional por um fluxo dinâmico composto por **5 perguntas obrigatórias de Sim ou Não**.
*   **Perguntas Variáveis (Wording Dinâmico):** Configure as perguntas para variarem de formulação a cada carregamento ou através de uma lista de opções predefinidas, mantendo exatamente o mesmo cunho e sentido original para manter o questionário dinâmico. Exemplos de variações:
    1.  **Entregas e Resultados:**
        *   Variação A: *"O liderado atingiu as principais metas/entregas combinadas para este período?"* (Sim / Não)
        *   Variação B: *"As metas prioritárias pactuadas para este ciclo foram devidamente cumpridas pelo colaborador?"* (Sim / Não)
        *   Variação C: *"O liderado entregou os resultados chaves esperados para este período dentro do prazo?"* (Sim / Não)
        *   *Se resposta indicar atenção (**Não**), abra o campo opcional (sem tamanho mínimo de caracteres):* *"O que faltou para a entrega?"*
    2.  **Alinhamento Cultural:**
        *   Variação A: *"O liderado demonstrou comportamentos alinhados aos valores da cultura da empresa?"* (Sim / Não)
        *   Variação B: *"As atitudes do colaborador refletiram a cultura e os valores essenciais da organização neste ciclo?"* (Sim / Não)
        *   Variação C: *"O liderado agiu em conformidade com as diretrizes culturais da nossa empresa?"* (Sim / Não)
        *   *Se resposta indicar atenção (**Não**), abra o campo opcional (sem tamanho mínimo de caracteres):* *"Qual comportamento precisa ser corrigido?"*
    3.  **Necessidade de Evolução:**
        *   Variação A: *"Identificou algum gargalo ou ponto de desenvolvimento (técnico ou comportamental) que precisa de ajuste imediato?"* (Sim / Não)
        *   Variação B: *"Houve algum obstáculo técnico ou comportamental do colaborador que demande desenvolvimento prioritário?"* (Sim / Não)
        *   Variação C: *"Foi observado algum gap ou gargalo de capacitação que requer atenção corretiva rápida?"* (Sim / Não)
        *   *Se resposta indicar atenção (**Sim**), abra o campo opcional (sem tamanho mínimo de caracteres):* *"Descreva a situação ou comportamento a ser corrigido."*
    4.  **Suporte do Líder:**
        *   Variação A: *"O liderado possui alguma barreira ou obstáculo externo impedindo sua evolução atual?"* (Sim / Não)
        *   Variação B: *"Existe algum bloqueio externo, de infraestrutura ou de processos impedindo a evolução do colaborador?"* (Sim / Não)
        *   Variação C: *"Há alguma barreira fora do controle direto do liderado que está travando o seu desenvolvimento?"* (Sim / Não)
        *   *Se resposta indicar atenção (**Sim**), abra o campo opcional (sem tamanho mínimo de caracteres):* *"Como o líder ou a empresa podem ajudar a destravar?"*
    5.  **Foco no Futuro (PDI):**
        *   Variação A: *"Ficou claro e definido o plano de ação/próximos passos do liderado até o próximo encontro?"* (Sim / Não)
        *   Variação B: *"Os próximos passos e acordos de PDI do colaborador até a próxima 1:1 foram combinados com clareza?"* (Sim / Não)
        *   Variação C: *"Ficou estabelecido um plano de ação nítido para as tarefas do liderado até a próxima conversa?"* (Sim / Não)
        *   *Se resposta indicar atenção (**Sim**), abra o campo opcional (sem tamanho mínimo de caracteres):* *"Quais as principais ações combinadas?"*
*   **Campos de Texto Opcionais e sem Tamanho Mínimo:** Todos os campos textuais condicionais que se abrem após o Sim/Não são **estritamente opcionais** e **não devem possuir validação de tamanho mínimo** de caracteres (o líder pode submeter sem preenchê-los ou digitar textos curtos).
*   **Observações Gerais:** Ao final do formulário, inclua um campo textual de dissertação geral e opcional (máximo 500 caracteres) para que o líder adicione anotações livres, elogios ou notas extras.
*   **Nota de Conformidade (LGPD):** Exiba de forma visível uma mensagem informando que este registro é confidencial e protegido, e que o time de RH terá acesso estritamente aos indicadores analíticos globais e metadados de frequência, preservando os detalhes descritivos confidenciais.
*   **Botão 'Enviar para Análise':** Deve habilitar assim que as 5 respostas de Sim/Não forem preenchidas, independentemente dos campos opcionais de texto estarem vazios ou preenchidos. Ao clicar, exiba uma tela de carregamento (overlay) com spinner e a mensagem: *"A IA da MPB está estruturando e moderando o seu feedback..."*.

### 6. Integração com IA (Análise, Extração SBI e Moderação de Tom)
*   **Chamada da IA:** Se a Gemini API Key estiver configurada, faça a chamada real HTTPS para a API do Gemini. Caso contrário, simule o retorno de inteligência artificial com um delay de 2 segundos.
*   **Mapeamento SBI e Instruções da IA:** A IA deve cruzar as respostas Sim/Não, as descrições dos campos condicionais e as observações gerais para estruturar automaticamente um feedback formal no padrão **SBI (Situation, Behavior, Impact - Situação, Comportamento, Impacto)** mais uma **Recomendação de PDI** clara e acionável.
    *   **CRÍTICO - CONSISTÊNCIA DE CONTEÚDO:** A IA (e o motor de Sandbox local de mock) deve refletir fielmente a **verdade factual da avaliação**. Se o líder marcou **NÃO** para cumprimento de metas, alinhamento de valores ou inseriu críticas de baixo desempenho nas observações, a IA **NUNCA** deve florear ou criar contradições positivas (como afirmar que o colaborador manteve engajamento exemplar ou recomendar PDI de promoção para o próximo nível de senioridade). A IA deve manter o diagnóstico de gap de performance, mas traduzido em tom corporativo, polido e focado em um plano de melhoria e recuperação imediata de entregas.
*   **Moderação de Tom, LGPD e Direitos Humanos:**
    *   A IA deve atuar como um guardião estrito de conformidade à LGPD e aos Direitos Humanos.
    *   Ela deve analisar as entradas de texto livre do líder, identificar e remover de forma absoluta qualquer linguagem inadequada, rude, agressiva, ofensiva, intimidadora ou depreciativa.
    *   **Higienização de Dados Sensíveis e Proteção à Saúde (LGPD):** Qualquer informação que exponha diagnósticos de saúde específicos (como "depressão"), nomes de médicos, psicólogos ou clínicas deve ser totalmente omitida para proteção de dados sensíveis. Contudo, em vez de ignorar a situação do colaborador, a IA deve **generalizar e apoiar a questão**, registrando que o colaborador relatou estar enfrentando *'desafios pessoais de saúde'* ou *'questões temporárias de bem-estar/saúde mental'*.
    *   **Reconstrução para Crítica Construtiva e Apoio:** Toda queixa ou comentário ríspido deve ser transformado em um feedback construtivo rico e formal, com foco em desenvolvimento. A recomendação de PDI deve incluir, de forma empática e respeitosa, ações de acolhimento e suporte, direcionando a colaboradora aos programas de assistência interna da empresa ou sugerindo/encorajando que busque suporte de saúde especializado e profissional.
    *   **Exemplo Prático de Transformação (A IA e a simulação de Mock devem seguir este padrão exato):**
        *   *Texto de Entrada do Líder (Rude/Irregular):* *"A Ana foi muito devagar e preguiçosa nessa sprint. Ela é muito burra e não consegue entender coisas simples. Além disso, ela fica de fofoca sobre a depressão dela com o psicólogo João Silva da Clínica X. Quero que melhore ou vou demitir."*
        *   *Saída Higienizada, Estruturada e Empática pela IA:*
            *   *Situação:* *"Durante a execução do ciclo recente de desenvolvimento técnico da equipe."*
            *   *Comportamento:* *"A colaboradora apresentou oscilações no ritmo de entrega e dificuldades na absorção de instruções operacionais, relatando desafios pessoais de saúde que têm impactado suas atividades cotidianas."*
            *   *Impacto:* *"Esse cenário afetou temporariamente o cronograma final do projeto e exigiu esforço adicional de suporte e redistribuição de tarefas entre o time."*
            *   *Recomendação de PDI:* *"Fornecer suporte técnico contínuo e checkpoints diários para acompanhamento próximo, oferecer maior flexibilidade de prazos nas próximas tarefas e orientá-la com empatia a buscar apoio profissional de saúde ou canais de assistência interna da empresa, priorizando seu bem-estar integral durante o processo de recuperação de desempenho."*
*   **Simulação de Fallback (Mock):** Caso a API Key não esteja configurada, a simulação local deve aplicar exatamente essa lógica de mapeamento rica. Ela deve ler a entrada do usuário e, se detectar termos negativos, informais ou referências de saúde, deve sanitizá-los e convertê-los em alternativas formais e empáticas no formato SBI + PDI conforme o exemplo prático acima.
*   Ao concluir o processamento, redirecione o usuário para a Tela de Revisão SBI.

### 7. Tela de Revisão do Feedback SBI e Assinatura (`/revisao-sbi` - Exclusivo do Líder)
*   Exiba o banner de atenção no topo: *"⚠️ Lembre-se: O líder humano é o único responsável pelo feedback final. Revise as sugestões da IA e edite o que for necessário."*
*   Exiba 4 caixas de texto editáveis (`textarea`) preenchidas com o resultado da IA: **Situação**, **Comportamento**, **Impacto** e **Recomendação de PDI**. O líder pode modificar qualquer um dos textos.
*   **Termo de Ciência e Assinatura:** No rodapé, apresente o termo de concordância ("Declaro que realizei a sessão de 1:1 e concordo com os pontos acordados..."). Adicione um campo para o líder assinar digitalmente (digitar o nome completo ou fazer uma assinatura em canvas de desenho).
*   **Ação:** Botão **'Salvar e Enviar para o Liderado'**. Ao clicar, salva o registro no `localStorage` com o status de `Pendente de Assinatura do Liderado` e redireciona o líder para seu histórico.

### 8. Painel do Liderado e Autenticação de Assinatura (`/meu-painel` - Exclusivo do Liderado)
*   Ao logar como Liderado, o colaborador visualiza seu histórico de feedbacks anteriores e um card em destaque com avisos de reuniões pendentes de ciência.
*   Ao abrir um feedback com status `Pendente de Assinatura do Liderado`:
    *   Exiba **apenas a Análise SBI (Situação, Comportamento, Impacto e Recomendação de PDI)** gerada e moderada pela IA (LGPD/Direitos Humanos) e revisada pelo líder. Não exiba as respostas brutas Sim/Não nem as anotações rascunhadas originais do líder.
    *   Exiba o Termo de Ciência do Liderado.
    *   **Fluxo de Autenticação Obrigatória:** Ao clicar em 'Autenticar e Assinar', abra um modal simulando o envio de um token de segurança de 6 dígitos para o e-mail do colaborador. Exiba o código gerado na tela de forma amigável (para fins de simulação/teste rápido).
    *   O colaborador insere o token de validação, digita seu nome completo como assinatura e confirma.
    *   O status da reunião no `localStorage` muda para `Concluído e Assinado`.

### 9. Geração de PDF e Envio por E-mail (Simulação e Automação)
*   Logo após a autenticação e conclusão do 1:1 pelo liderado, o sistema deve:
    1.  Gerar automaticamente um arquivo PDF estilizado e formatado usando a biblioteca `jspdf` contendo **apenas a Análise SBI (Situação, Comportamento, Impacto e Recomendação de PDI) moderada pela IA (LGPD/DH)**, além do cabeçalho com metadados (líder, liderado, data, área) e os logs de assinaturas e data/hora da autenticação eletrônica. Não inclua no PDF as respostas binárias brutas nem os rascunhos originais do líder.
    2.  Simular o disparo de um e-mail com o arquivo PDF em anexo para o e-mail do liderado.
    3.  Apresentar um painel ou aba chamada **'Simulador de E-mails'** acessível no rodapé ou no menu, simulando a caixa de entrada de e-mails do Diego Santos (`colaborador@empresa.com`). O usuário poderá clicar nessa aba e abrir o e-mail recebido com o assunto *"Seu Relatório de 1:1 - MPB"*, podendo baixar e visualizar o PDF gerado diretamente por lá.

### 10. Área de Feedback Bidirecional (`/feedback-bidirecional`)
*   **Acesso do Líder e Liderado:** Permita que tanto o Líder quanto o Liderado preencham avaliações periódicas mútuas para monitorar o alinhamento da relação de trabalho.
*   **Filtro e Correção de Tom por IA:** Qualquer comentário em texto livre digitado nas avaliações mútuas deve passar obrigatoriamente pela **mesma inteligência artificial de moderação** (com mock correspondente de delay de 2 segundos), higienizando dados sensíveis segundo a LGPD/DH e convertendo críticas ásperas em críticas construtivas e profissionais.
*   **Privacidade e Acesso do RH (Feedbacks Privados e Visão do RH):** Os feedbacks e avaliações bidirecionais salvos são privados, visíveis apenas para os dois envolvidos diretamente (quem enviou e quem recebeu), sem acesso a outros líderes ou colaboradores externos. O time de RH também possui a função exclusiva de visualizar esses relatórios de feedback bidirecional singular (detalhado por colaborador, ex: `COL-01`), mas qualquer texto exibido ao RH deve passar estritamente pela moderação e correção da IA (LGPD e Direitos Humanos) para garantir sigilo de diagnósticos de saúde e tom puramente construtivo.
*   **Formulário do Liderado (Avaliação do Líder):**
    *   5 perguntas objetivas de 1 a 5 estrelas sobre: 'Suporte no PDI', 'Qualidade da Comunicação', 'Clareza de Expectativas', 'Segurança Psicológica' e 'Disponibilidade para Apoio'.
    *   Campo de texto opcional: *"O que o líder poderia fazer de diferente para apoiar meu crescimento?"* (Esse texto deve passar pela moderação/correção de IA antes de ser salvo/enviado).
*   **Formulário do Líder (Avaliação da Parceria):**
    *   5 perguntas objetivas de 1 a 5 estrelas sobre: 'Proatividade', 'Receptividade a Feedbacks', 'Comunicação', 'Resolução de Conflitos' e 'Compromisso com o PDI'.
    *   Campo de texto opcional: *"Observações sobre a dinâmica de colaboração."* (Esse texto deve passar pela moderação/correção de IA antes de ser salvo/enviado).
*   Permita que ambos visualizem o histórico consolidado de feedbacks privados trocados entre si.

### 11. Portal de Dashboard do RH (`/dashboard-rh` - Exclusivo do RH)
*   **Portal de People Analytics:** Visão macro global voltada à gestão de pessoas da empresa.
*   **Conformidade à LGPD e Anonimização:** A tela inicial do RH deve exibir apenas IDs anonimizados (ex: `COL-01`), sem expor nomes de colaboradores ou de líderes.
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
        4.  *Feedbacks Bidirecionais Singulares:* Lista das avaliações mútuas individuais trocadas pelo colaborador (enviadas e recebidas com estrelas e texto), com todos os comentários textuais moderados/corrigidos pela IA (respeitando LGPD/DH).
        5.  *Evolução de PDI:* Barra de progresso visual de conclusão de metas de PDI combinadas ao longo do tempo (ex: 'Progresso de PDI: 80%').
        6.  *Mapeamento de Levels (L1, L2, L3):* Exiba o mapeamento interativo do nível atual do colaborador e as competências esperadas, indicando de forma visual quais competências foram alcançadas e quais estão em desenvolvimento de acordo com as avaliações de PDI anteriores.

### 12. Manual do Sistema Integrado (Acessível via Menu em `/app`)
*   Adicione o link **"Manual & Sobre"** no menu do cabeçalho da aplicação `/app.html` para todos os perfis (Líder, Liderado, RH).
*   Ao clicar nesse link, o sistema deve exibir uma tela estilizada contendo o manual técnico-operacional do sistema estruturado da seguinte forma:
    1.  *Descrição do Sistema:* Finalidade de aproximar a liderança de suas equipes por People Analytics e SBI estruturado.
    2.  *Principais Funcionalidades:* Lista contendo a descrição das features desenvolvidas.
    3.  *Não Funcional (Mocks):* Detalhamento das limitações técnicas do protótipo (SMTP simulado, API sandbox local sem API Key, dados em localStorage).
    4.  *Sugestões de Evoluções:* Próximos passos e melhorias de arquitetura.
    5.  *Equipe e Grupo:* Nome do grupo e integrantes.

### 13. Portal de Lançamento e Repositório Git (Acessível via `/` ou `index.html`)
*   A página raiz da aplicação (`index.html`) deve ser uma vitrine contendo uma navegação limpa baseada em abas com os seguintes conteúdos:
    1.  *Aba 🏠 Lançamento:* Apresenta a marca MPB Conexão Humana, valor estratégico, métricas chaves e botões de chamada de ação para iniciar o MVP funcional.
    2.  *Aba 💻 Repositório Git:* Interface que simula de forma visual a estrutura de repositório no GitHub para `joaos/mpb-conexao-humana`. Contém uma barra lateral com a árvore de arquivos do projeto (`site/app.html`, `site/index.html`, `docs/lovable-prompt.md`, `docs/business-context-lite.md`, `README.md`) e um visualizador de código interativo que carrega o código/descrição de cada arquivo selecionado, além de uma sub-aba mostrando o histórico dos commits recentes realizados.
    3.  *Aba 📖 Manual & Sobre:* Exibe o manual completo do sistema estruturado (com as 5 seções descritas na seção anterior)."
