# Fluxo de Telas do Aplicativo — Modelo de Questionário de Fechamento

Este documento descreve as telas e as jornadas do usuário, mapeadas diretamente às histórias de usuário especificadas no contexto de negócio.

## 📱 Fluxo do Líder e Liderado (Jornada Síncrona de 1:1)

1.  **Tela de Preparação [US01]:** 
    *   O líder seleciona o colaborador da sua lista de liderados.
    *   O sistema exibe o nível atual do colaborador no Framework de Levels e sugere pelo menos 2 perguntas de desenvolvimento personalizadas.
    *   Um botão "Iniciar Reunião" leva para a tela de condução.
2.  **Tela de Condução:**
    *   Exibe o roteiro e as perguntas sugeridas para guiar a conversa cara a cara. (Não há registros neste momento).
3.  **Tela do Questionário de Fechamento (Os 5 minutos finais) [US02]:**
    *   O líder preenche três perguntas fechadas obrigatórias de Sim/Não (Alinhamento de PDI, Bloqueios de Infraestrutura e Dificuldades Técnicas).
4.  **Tela de Dissertação Executiva [US02]:**
    *   O líder preenche um campo de texto aberto resumindo a conversa, os combinados e o desempenho.
    *   Um botão "Enviar para Análise" aciona o motor de IA (`POST /api/meetings/close`).
5.  **Tela de Revisão do Feedback SBI [US03]:**
    *   Exibe em tempo real o feedback estruturado pela IA nas seções de Situação, Comportamento e Impacto (SBI), além de recomendações para o PDI.
    *   Permite que o líder edite qualquer um dos blocos gerados (Human-in-the-loop) antes do salvamento final na base.

---

## 📊 Fluxo do RH (Dashboard Analítico)

1.  **Painel de Controle e Métricas Gerais (People Analytics) [US04]:**
    *   Exibição de gráficos agregados gerados a partir das respostas binárias (Taxa de alinhamento de PDI por área, gargalos técnicos sistêmicos).
2.  **Painel de Prontidão e Promoção [US04]:**
    *   Uma listagem gerada de forma agregada contendo os colaboradores sinalizados no log higienizado de RH como "Elegíveis para promoção de nível" (ex: Júnior para Pleno, Pleno para Sênior).
3.  **Painel de Alertas de Risco (eNPS / Turnover) [US04]:**
    *   Indicação visual de equipes que apresentam altos índices de bloqueio ou falta de reuniões em atraso (RN04) para que o RH realize intervenções preventivas de retenção.

