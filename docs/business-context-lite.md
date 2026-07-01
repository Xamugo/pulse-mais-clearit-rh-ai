# Contexto de Negócio Lite - Projeto Pulse Mais & ClearIT

## 1. Visão Geral e Objetivo do Produto
O objetivo deste produto é desenvolver um agente de Inteligência Artificial focado em apoiar e capacitar líderes da ClearIT na preparação, condução e registro de reuniões de feedback e 1:1 (One-on-One). O produto visa transformar o RH de um setor reativo em uma área estratégica orientada a dados, reduzindo o turnover e aumentando o índice de eNPS.

## 2. Alinhamento do Problema (Dores do Cliente)
Com base na imersão e mapeamento com o RH, a solução ataca diretamente as seguintes dores estruturais:
* **Cultura de Não Registro:** Reuniões de 1:1 e feedbacks acontecem, mas não são documentados de forma centralizada. Perde-se o histórico e o RH fica "no escuro".
* **Desvio Operacional (Reunião de Status):** Líderes técnicos ou em transição gastam o tempo de desenvolvimento de pessoas apenas cobrando entregas e tarefas do dia a dia.
* **Feedbacks Acumulados:** Prática de acumular feedbacks para "despejá-los" apenas nas avaliações de desempenho anuais.
* **Inexistência de Dados Analíticos:** Comunicação descentralizada (Teams, e-mail, conversas físicas) impossibilitando a identificação de riscos de desengajamento ou problemas sistêmicos nas áreas.

## 3. Conceitos Pesquisados e Soluções com Uso de IA
Para solucionar o problema sem gerar fricção ou burocracia para o usuário (Garantindo que a ferramenta seja maior que o esforço), mapeamos as seguintes soluções de IA:
1. **Pautas Inteligentes Automatizadas:** Cruzamento automático do cargo do liderado e sua régua de competências (**Framework de Levels**) para sugerir perguntas personalizadas de carreira antes da reunião.
2. **Estruturação de Texto (Modelo SBI):** O líder insere notas rápidas (por texto ou voz transcrita) e a IA organiza o feedback na estrutura correta: *Situação, Comportamento e Impacto*.
3. **Mecanismo de Guardrails e LGPD:** Filtro em tempo real que impede o registro de dados sensíveis e adverte o líder caso identifique linguagem inadequada ou tóxica.
4. **Dashboard Preditivo de Tendências para o RH:** Leitura anonimizada dos registros para alertar o RH sobre riscos de turnover e mapear o nível de maturidade da liderança (Iniciante, Em Desenvolvimento, Consistente, Referência).

## 4. Definição de Sucesso do Projeto (Métricas)
Para o cliente, o sucesso do projeto será medido através de:
* **Adesão e Cadência:** % de líderes que realizam e registram as reuniões de 1:1 em um intervalo máximo de 30 dias.
* **Qualidade dos Feedbacks:** Redução de feedbacks puramente operacionais e aumento de registros estruturados em formato de desenvolvimento de carreira.
* **Métricas de Clima:** Recuperação e alta nos índices de Liderança, Confiança e eNPS geral nas pesquisas de clima subsequentes.

## 5. Alinhamento de Escopo para a PoC (Prova de Conceito)
* **O que será testado na PoC:** A capacidade técnica da IA em classificar e estruturar textos soltos no formato SBI, a eficácia dos prompts de geração de pauta usando o Framework de Levels e a assertividade do filtro de segurança (Guardrails).
* **Restrição Crítica da PoC:** Uso exclusivo de **dados fictícios e simulados** para proteção de privacidade e conformidade com a LGPD, operando isolado dos sistemas de produção da ClearIT.
