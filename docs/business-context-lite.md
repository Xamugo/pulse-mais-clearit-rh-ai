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
    1. Dado que o líder acessa a tela de preparação, quando seleciona um colaborador, então o sistema deve exibir seu cargo atual e as competências esperadas de acordo com o Framework de Levels.
    2. Dado o nível do colaborador, quando a pauta é gerada, então o sistema deve fornecer no mínimo 2 perguntas de desenvolvimento específicas para o nível (ex: sugestões de PDI ou desafios de carreira).
    3. Dado a exibição das sugestões, quando o líder decide iniciar a conversa, então deve haver um botão de ação rápida para ir para a tela de visualização do roteiro de forma imediata.

#### **US02 — Registro Quanti-Qualitativo Rápido (F01)**
*   **Como** líder,  
*   **Quero** registrar respostas rápidas de Sim/Não e uma breve dissertação argumentativa do encerramento da 1:1,  
*   **Para** formalizar os acordos da conversa em menos de 5 minutos, sem gerar barreiras de burocracia ou uso de áudio.
*   **Critérios de Aceite:**
    1. Dado o término da conversa de 1:1, quando o líder aciona a tela de fechamento, então o sistema deve apresentar perguntas binárias fechadas obrigatórias (sobre alinhamento de PDI, bloqueios externos e prazos).
    2. Dado o preenchimento das perguntas de Sim/Não, quando o líder acessa o campo de texto livre, então o sistema deve apresentar um campo dissertativo incentivando o resumo objetivo da performance e combinados.
    3. Dado que o líder finaliza o formulário, quando clica em enviar, então as respostas devem ser salvas de forma síncrona.

#### **US03 — Geração de Feedback SBI via IA (F03)**
*   **Como** líder (especialmente em transição técnico-gestão),  
*   **Quero** que a Inteligência Artificial processe a dissertação corrida que escrevi e a organize no modelo Situação, Comportamento e Impacto (SBI),  
*   **Para** que eu possa ter um relatório formatado de feedback profissional, reduzindo o meu viés subjetivo e gerando ações práticas.
*   **Critérios de Aceite:**
    1. Dado que a dissertação corrida foi enviada ao servidor, quando o motor de IA processa o texto, então deve retornar blocos específicos estruturados nas chaves de Situação (contexto), Comportamento (fato observado) e Impacto (consequência).
    2. Dado o relatório SBI gerado, quando exibido para o líder na interface, então deve sugerir ao menos uma recomendação de ação prática ou combinado para o Plano de Desenvolvimento Individual (PDI).
    3. Dado o feedback estruturado gerado pela IA, quando exibido na tela de revisão, então o líder deve ter a opção de editar o texto antes de enviá-lo de forma final (Garantia de Human-in-the-loop).

#### **US04 — Relatório Anonimizado e Higienizado para o RH (F04 & F05)**
*   **Como** gerente de RH (Priscila Bacelar),  
*   **Quero** receber relatórios das reuniões em formato macro, higienizados de dados sensíveis e com as categorizações de desenvolvimento geradas por IA,  
*   **Para** monitorar a evolução dos times e riscos organizacionais de forma agregada, mantendo total sigilo individual e segurança jurídica.
*   **Critérios de Aceite:**
    1. Dado o processamento de uma dissertação pela IA, quando houver referências a dados pessoais identificáveis (nomes, CPFs, condições de saúde, faixa salarial), então a IA deve limpar ou omitir esses dados antes de repassar os registros à base acessível pelo RH.
    2. Dado a validação qualitativa do texto pela IA, quando o processamento termina, então o sistema deve gerar indicadores macros com o status do PDI (Ativo/Inativo), identificação de barreiras comportamentais e prontidão para evolução de cargo (Júnior/Pleno/Sênior).
    3. Dado o acesso do RH ao dashboard analítico, quando visualizados os índices consolidados de People Analytics, então o sistema deve apresentar as informações de forma agregada (gráficos de pizza/barras por área), impedindo a identificação de indivíduos específicos em turmas pequenas.

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

