# Contexto de Negócio (SSOT de Produto) — Pulse Mais & ClearIT

## 1. Visão do Produto
O **Pulse Mais** é um assistente de Inteligência Artificial integrado ao processo de gestão de pessoas da **ClearIT**. O produto apoia os líderes de equipe na preparação, condução e fechamento ágil de reuniões de 1:1 e feedbacks estruturados. O objetivo é eliminar as barreiras de documentação das conversas de liderança, substituindo rotinas complexas por um questionário síncrono de fechamento quanti-qualitativo de 5 minutos, municiando o RH de dados analíticos em tempo real (People Analytics) para a tomada de decisões de carreira, retenção de talentos e melhoria do clima (eNPS).

*   **Fora do escopo (não-objetivos):** 
    *   Gravação direta e armazenamento de áudio ou vídeo das reuniões.
    *   Uso de dados pessoais sensíveis reais no MVP (armazenamento de CPF, saúde, salários).
    *   Integração automática e bidirecional em tempo real com sistemas de produção legados ou plataforma Sólides neste estágio (a exportação de relatórios será feita em formatos manuais como CSV ou PDF).

## 2. Público & Personas

| Persona | Quem é (Perfil) | Contexto e Dores no Uso | Diretrizes para o Agente de IA |
|---|---|---|---|
| **Líder Técnico** | Desenvolvedores seniores ou arquitetos de software promovidos recentemente à liderança de times. | Baixa tolerância a processos percebidos como burocracia de RH. Entra nas reuniões sem roteiro estruturado e improvisa. | Gerar roteiros e pautas de 1:1 extremamente diretos, focados em soluções técnicas e desenvolvimento, sem jargões de RH. |
| **Líder em Transição** *(Coordenador)* | Gestor iniciante com responsabilidade formal sobre pessoas, mas sem experiência prévia. | Falta de repertório emocional para lidar com conflitos e conduzir feedbacks corretivos. Medo de parecer agressivo ou injusto. | Fornecer pautas passo a passo super detalhadas, sugestões de frases de apoio e estruturar os feedbacks no modelo SBI de forma neutra. |
| **Líder Engajado** | Gestor experiente que acredita fortemente nas 1:1s e prioriza a gestão de pessoas. | Gargalo de tempo para planejar pautas personalizadas e dificuldades para gerenciar a cadência regular com grandes equipes. | Agilizar a estruturação dos registros pós-reunião e organizar pautas com base no histórico anterior de forma automatizada. |
| **Gerente de RH** *(Priscila Bacelar)* | Responsável por monitorar o clima, planos de desenvolvimento e calibração de performance. | O RH trabalha apagando incêndios por não ter visibilidade analítica da qualidade e frequência das 1:1s nas áreas. | Consolidar dados macros anonimizados de People Analytics (riscos de turnover, status de PDI e prontidão de promoção) sem ferir a LGPD. |

### 2.1. Framework de Levels de Referência (Dados da PoC)
A plataforma utiliza a seguinte régua de cargos e competências comportamentais/técnicas simulada para a ClearIT:

*   **L1 — Colaborador Júnior (Júnior):**
    *   *Autonomia Técnica:* Executa tarefas básicas de desenvolvimento sob supervisão constante; documenta as tarefas de forma satisfatória; reporta impedimentos logo que ocorrem.
    *   *Trabalho em Equipe:* Comunica-se de forma clara nas reuniões diárias; compartilha conhecimento básico; colabora construtivamente com o time.
    *   *Qualidade de Entrega:* Escreve códigos funcionais simples; corrige defeitos básicos identificados no code review.
*   **L2 — Colaborador Pleno (Pleno):**
    *   *Resolução de Problemas:* Propõe e implementa soluções para problemas de complexidade média de forma autônoma; sabe identificar trade-offs simples de performance.
    *   *Mentoria:* Auxilia no onboarding de novos colaboradores do time; tira dúvidas e apoia no desenvolvimento de nível L1.
    *   *Comunicação Técnica:* Explica decisões arquiteturais simples e documenta fluxos de forma clara para que qualquer membro do time entenda.
*   **L3 — Colaborador Sênior (Sênior):**
    *   *Liderança Técnica:* Conduz discussões arquiteturais complexas; define padrões de código; atua proativamente mitigando gargalos e riscos de escalabilidade.
    *   *Impacto de Negócio:* Conecta as decisões de engenharia aos objetivos estratégicos da organização; possui visão de negócio e produto.
    *   *Mentoria e Cultura:* Atua como mentor ativo de colaboradores L2 e L1; influencia positivamente a cultura de qualidade técnica da ClearIT.

## 3. Dores do Cliente (Problemas que resolvemos)

| Dor Mapeada | Impacto no Negócio (O que custa hoje) | Solução da Plataforma |
|---|---|---|
| **Cultura de Não Registro** | Perda de histórico, falta de continuidade de PDIs e o RH fica completamente "no escuro". | Formulário síncrono rápido de 5 minutos ao fim de cada reunião com gravação imediata na base. |
| **Reuniões Operacionais (Status)** | Conversas focam apenas em cobranças técnicas, sacrificando conversas de carreira e desenvolvimento. | Geração de pautas inteligentes baseadas no Framework de Levels do colaborador. |
| **Acúmulo de Feedbacks** | Colaboradores recebem feedbacks corretivos apenas nas avaliações anuais, gerando surpresas e desengajamento. | Estímulo a feedbacks pontuais e acompanhamento de cadência no sistema. |
| **Ausência de Dados Estruturados** | Queda no eNPS e no índice de Liderança e Confiança sem que o RH consiga mapear a origem do problema. | Dashboard de People Analytics com gráficos consolidados por área e alertas de risco. |

## 4. Objetivos & Métricas de Sucesso
*   **Objetivo de Adoção:** Garantir que 100% da liderança da ClearIT registre reuniões de 1:1 regularmente.
    *   *Como medimos:* Taxa de preenchimento de formulários de 1:1 por líder dentro do ciclo de 15 a 30 dias.
*   **Objetivo de Clima Organizacional:** Recuperar e elevar o índice de Liderança e Confiança nas pesquisas de clima corporativas de 2027.
    *   *Como medimos:* Notas das dimensões de "suporte ao desenvolvimento" e eNPS por área.
*   **Objetivo Técnico:** Viabilizar uma solução de análise qualitativa de feedbacks sem infringir a LGPD.
    *   *Como medimos:* Taxa de descarte/higienização de dados pessoais sensíveis identificada pelo motor de IA.

## 5. Backlog de Épicos e Features

### Matriz de Funcionalidades x Estado

| ID | Funcionalidade (Feature) | Prioridade | Estado Atual | Notas / Evidências |
|---|---|---|---|---|
| **F01** | Entrada de Dados do Questionário de Fechamento | Alta | A Fazer | Entrada quanti-qualitativa de dados pelo líder. |
| **F02** | Pautas Inteligentes Baseadas no Framework de Levels | Alta | A Fazer | Sugestões automáticas de perguntas de desenvolvimento. |
| **F03** | Processamento de Feedback SBI por IA | Alta | Concluído (PoC) | Transformação de textos dissertativos no formato SBI. |
| **F04** | Higienização e Relatório Executivo para o RH por IA | Alta | Concluído (PoC) | Remoção de dados sensíveis e geração de logs macro. |
| **F05** | Dashboard Analítico de People Analytics | Média | A Fazer | Painel gerencial com gráficos consolidados para o RH. |

---

## 6. Especificações Ativas (Em Detalhe)

### User Stories (Histórias de Usuário)

#### **US01 — Preparação Inteligente de Reuniões (F02)**
*   **Como** líder de equipe (técnico, em transição ou engajado),  
*   **Quero** visualizar o nível atual do meu liderado no Framework de Levels e receber sugestões automáticas de perguntas de desenvolvimento,  
*   **Para** que eu possa estruturar e direcionar uma conversa de carreira relevante sem gastar tempo com preparação manual complexa.
*   **Critérios de Aceite:**
    *   **Cenário 1: Seleção de Colaborador L1 (Júnior)**
        *   **Dado** que o líder está na tela de preparação de 1:1,
        *   **Quando** ele seleciona um colaborador com cargo cadastrado no nível "L1 (Júnior)",
        *   **Então** o sistema deve renderizar o cargo "Júnior" na interface e exibir as perguntas de desenvolvimento:
            1. *"Como você está se sentindo em relação à sua autonomia diária nas tarefas da Sprint? Onde sente mais bloqueios?"*
            2. *"Houve alguma oportunidade de colaborar com outros colegas que você gostaria de destacar?"*
    *   **Cenário 2: Seleção de Colaborador L2 (Pleno)**
        *   **Dado** que o líder está na tela de preparação de 1:1,
        *   **Quando** ele seleciona um colaborador com cargo cadastrado no nível "L2 (Pleno)",
        *   **Então** o sistema deve renderizar o cargo "Pleno" na interface e sugerir as perguntas de desenvolvimento:
            1. *"Como tem sido a experiência de tirar dúvidas e apoiar os colegas iniciantes do time?"*
            2. *"Que tipo de problema técnico de média complexidade você liderou ou resolveu autonomamente recentemente?"*
    *   **Cenário 3: Seleção de Colaborador L3 (Sênior)**
        *   **Dado** que o líder está na tela de preparação de 1:1,
        *   **Quando** ele seleciona um colaborador com cargo cadastrado no nível "L3 (Sênior)",
        *   **Então** o sistema deve renderizar o cargo "Sênior" na interface e sugerir as perguntas de desenvolvimento:
            1. *"Como as suas decisões arquiteturais recentes impactaram a escalabilidade e os objetivos de negócio da ClearIT?"*
            2. *"De que forma você está estruturando sua mentoria para elevar a maturidade técnica dos colaboradores L2?"*

#### **US02 — Registro Quanti-Qualitativo Rápido (F01)**
*   **Como** líder,  
*   **Quero** registrar respostas rápidas de Sim/Não e uma breve dissertação argumentativa do encerramento da 1:1,  
*   **Para** formalizar os acordos da conversa em menos de 5 minutos, sem gerar barreiras de burocracia ou uso de áudio.
*   **Critérios de Aceite:**
    *   **Cenário 1: Validação de Campos Obrigatórios**
        *   **Dado** que o líder está na tela de questionário de fechamento,
        *   **Quando** ele tenta clicar no botão "Enviar para Análise" sem marcar todas as 3 respostas de Sim/Não ou com a dissertação contendo menos de 100 caracteres,
        *   **Então** o sistema deve manter o botão "Enviar para Análise" desabilitado e exibir alertas visuais em vermelho nos campos pendentes.
    *   **Cenário 2: Validação de Limites de Texto**
        *   **Dado** que o líder está digitando a "Dissertação Executiva" do encerramento,
        *   **Quando** a quantidade de caracteres atinge 1000 caracteres,
        *   **Então** o sistema deve impedir a digitação de novos caracteres e exibir um contador de caracteres `1000/1000` em vermelho.
    *   **Cenário 3: Envio de Dados do Formulário**
        *   **Dado** que o formulário está preenchido corretamente (3 checkboxes marcados e texto de 150 caracteres),
        *   **Quando** o líder clica no botão "Enviar para Análise",
        *   **Então** o sistema deve desabilitar o botão de envio, exibir um elemento visual de carregamento (spinner) com a mensagem *"IA processando feedback síncrono..."* e realizar a chamada POST à API REST.

#### **US03 — Geração de Feedback SBI via IA (F03)**
*   **Como** líder (especialmente em transição técnico-gestão),  
*   **Quero** que a Inteligência Artificial processe a dissertação corrida que escrevi e a organize no modelo Situação, Comportamento e Impacto (SBI),  
*   **Para** que eu possa ter um relatório formatado de feedback profissional, reduzindo o meu viés subjetivo e gerando ações práticas.
*   **Critérios de Aceite:**
    *   **Cenário 1: Renderização dos Blocos Estruturados**
        *   **Dado** que a API retornou o JSON de processamento com sucesso,
        *   **Quando** a interface exibe a tela de revisão de feedback SBI,
        *   **Então** o sistema deve expor quatro caixas de texto editáveis: "Situação", "Comportamento", "Impacto" e "Ação de Desenvolvimento/PDI Sugerida" contendo os dados correspondentes retornados pela IA.
    *   **Cenário 2: Ajuste Humano (Human-in-the-loop)**
        *   **Dado** que o líder está revisando os blocos na tela,
        *   **Quando** ele edita manualmente o texto gerado em qualquer um dos blocos,
        *   **Então** o sistema deve aceitar a alteração e utilizá-la como o valor definitivo para o salvamento final.
    *   **Cenário 3: Confirmação e Encerramento da 1:1**
        *   **Dado** que o líder aprovou a redação final do feedback,
        *   **Quando** ele clica no botão "Salvar e Concluir",
        *   **Então** o sistema deve enviar as modificações para salvar no banco de dados, habilitar a geração de exportação em PDF e redirecionar o usuário à tela de listagem inicial com a notificação *"Reunião 10293 salva com sucesso!"*.

#### **US04 — Relatório Anonimizado e Higienizado para o RH (F04 & F05)**
*   **Como** gerente de RH (Priscila Bacelar),  
*   **Quero** receber relatórios das reuniões em formato macro, higienizados de dados sensíveis e com as categorizações de desenvolvimento geradas por IA,  
*   **Para** monitorar a evolução dos times e riscos organizacionais de forma agregada, mantendo total sigilo individual e segurança jurídica.
*   **Critérios de Aceite:**
    *   **Cenário 1: Higienização de PII (Dados Pessoais)**
        *   **Dado** que a dissertação inserida pelo líder contenha nomes próprios ("Pedro de Souza"), dados financeiros ("recebe R$ 7.200,00"), termos médicos ("gripe e atestado"),
        *   **Quando** a IA processa a dissertação,
        *   **Então** deve higienizar o texto e salvar no log do RH substituindo os dados sensíveis por termos genéricos, ex: `[COLABORADOR]`, `[SALÁRIO OMITIDO]` e `[CONDIÇÃO MÉDICA OMITIDA]`.
    *   **Cenário 2: Categorização do Log de RH**
        *   **Dado** que a IA processou qualitativamente a dissertação,
        *   **Quando** a API grava na tabela `RHAuditLog`,
        *   **Então** os campos `status_pdi`, `barreiras_comportamentais`, `prontidao_carreira` e `sinalizacao_risco_turnover` devem conter valores tipados de forma exata de acordo com a leitura semântica.
    *   **Cenário 3: Visualização por Área no Dashboard**
        *   **Dado** que a gerente de RH acessa o painel de People Analytics,
        *   **Quando** filtra as informações pela área de "Tecnologia",
        *   **Então** o sistema deve apresentar as notas agregadas das áreas e a lista de colaboradores sinalizados para promoção, omitindo os textos das dissertações para garantir confidencialidade de time.

---

### Regras de Negócio (RN)

*   **`RN01` — Conformidade Estrita à LGPD (Limitação de Dados):** É expressamente proibido o tráfego ou armazenamento de dados pessoais sensíveis dos colaboradores no banco de dados da aplicação. Informações como nome completo, CPF, matrícula corporativa, condições de saúde físicas/mentais, situação familiar, desabafos de cunho íntimo e valores exatos de salário devem ser descartados ou anonimizados. A IA servirá como guardrail ativo, higienizando qualquer entrada dissertativa.
*   **`RN02` — Filtro Organizacional (Antifofoca):** A Inteligência Artificial deve atuar filtrando as dissertações de fechamento, eliminando expressões com julgamentos de caráter pessoal ("ele é preguiçoso", "está de má vontade") ou opiniões sobre terceiros sem evidência. O relatório de saída para o RH deve conter apenas informações estruturadas de competências, bloqueios operacionais de infraestrutura e metas de desenvolvimento do PDI.
*   **`RN03` — Responsabilidade Humana (Human-in-the-loop):** A inteligência artificial atua exclusivamente como suporte e sugestão. O líder humano é o único responsável final pelas avaliações, feedbacks e acordos tomados. A interface da aplicação deve exibir um alerta lembrando o líder de revisar as saídas da IA antes de validá-las.
*   **`RN04` — Controle de Cadência e Alertas de Temperatura:** O sistema deve calcular a diferença de dias entre os registros de 1:1 de cada liderado. Caso um colaborador fique mais de 30 dias sem reunião registrada, um alerta visual deve ser emitido para o líder correspondente e um indicador consolidado de "colaboradores em atraso" deve ser enviado no relatório de RH.
*   **`RN05` — Padrão SBI Obrigatório para Avaliações:** Todo feedback registrado na ferramenta que indique comportamento que precise ser ajustado ou reconhecido deve seguir a estrutura SBI (Situação, Comportamento, Impacto). Feedbacks sem contextualização factual e impacto concreto serão bloqueados ou sinalizados para correção antes do salvamento final no banco de dados.

---

## 7. Validação de Escopo
O escopo para a PoC e o MVP foi validado e aprovado formalmente.

*   **Escopo aprovado em:** 2026-07-01
*   **Aprovado por:** Priscila Bacelar (Gerente de RH / ClearIT)
*   **Dentro do escopo:** Ingestão via formulário síncrono (perguntas Sim/Não + dissertação), estruturação SBI (Líder), higienização e People Analytics macro (RH), dados fictícios e greenfield.
*   **Fora do escopo:** Gravação de áudio, integração automática com bancos de produção (ERP/Plataforma Sólides) e dados reais identificáveis de funcionários no ambiente de testes.

---

## 8. 🔁 Redesenhos
*Acompanhamento de redesenhos e pivots de produto.*

| Data | Ciclo / Feature | O que muda no próximo ciclo (Motivação) |
|---|---|---|
| 2026-06-30 | Gravação de áudio -> Formulários | Substituição da captação de áudio contínua (cancelada por inibição de privacidade e custos de LGPD) por um formulário de fechamento ágil síncrono de 5 minutos, processado por IA. |


